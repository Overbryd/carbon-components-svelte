<script>
  /**
   * Set to `true` to select the current link
   * @type {boolean} [isSelected=false]
   */
  export let isSelected = false;

  /**
   * Specify the `href` attribute
   * @type {string} [href]
   */
  export let href = undefined;

  /**
   * Specify the text
   * @type {string} [text]
   */
  export let text = undefined;

  /**
   * Specify the icon props
   * @type {{ render: typeof import("carbon-icons-svelte/lib/Add16").default; skeleton: boolean; }} [icon]
   */
  export let icon = undefined;

  import { Icon } from "../../Icon";
</script>

<li class:bx--side-nav__item={true}>
  <a
    aria-current={isSelected ? 'page' : undefined}
    {href}
    class:bx--side-nav__link={true}
    class:bx--side-nav__link--current={isSelected}
    {...$$restProps}
    on:click>
    {#if icon}
      <div
        class:bx--side-nav__icon={true}
        class:bx--side-nav__icon--small={true}>
        <Icon {...icon} />
      </div>
    {/if}
    <span class:bx--side-nav__link-text={true}>{text}</span>
  </a>
</li>

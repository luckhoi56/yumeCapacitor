<script>
  import {
    Header,
    HeaderNav,
    HeaderNavItem,
    HeaderNavMenu,
    SideNav,
    SideNavItems,
    SideNavMenu,
    SideNavMenuItem,
    SideNavLink,
    SkipToContent,
    Content,
    Grid,
    Row,
    Column,
  } from "carbon-components-svelte";

  let isSideNavOpen = false;
</script>

<Header company="IBM" platformName="Carbon Svelte" bind:isSideNavOpen>
  <div slot="skip-to-content">
    <SkipToContent />
  </div>

  <HeaderNav>
    <HeaderNavItem href="/" text="Order Hien Co" />
    <HeaderNavItem href="/finishOrder" text="Order Da Xong" />
    <HeaderNavItem href="/yesterdayOrder" text="Order Hom Qua" />
    <HeaderNavItem href="/yesterdayOrder" text="Order Hom Qua" />
    <HeaderNavItem href="/openOrClose" text="Dong/Mo Cua Tiem" />

  </HeaderNav>
</Header>

<SideNav bind:isOpen={isSideNavOpen}>
  <SideNavItems>
    <SideNavLink href="/" text="Order Hien Co" />
    <SideNavLink href="/finishOrder" text="Order Da Xong" />
    <SideNavLink href="/yesterdayOrder" text="Order Hom Qua" />
    <SideNavLink href="/openOrClose" text="Dong/Mo Cua Tiem" />
  </SideNavItems>
</SideNav>


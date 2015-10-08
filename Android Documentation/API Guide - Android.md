


<!DOCTYPE html>
<html lang="en" class=" is-copy-enabled">
  <head prefix="og: http://ogp.me/ns# fb: http://ogp.me/ns/fb# object: http://ogp.me/ns/object# article: http://ogp.me/ns/article# profile: http://ogp.me/ns/profile#">
    <meta charset='utf-8'>
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta http-equiv="Content-Language" content="en">
    <meta name="viewport" content="width=1020">
    <meta content="origin-when-crossorigin" name="referrer" />
    
    <title>PrivateDocumentation/API Guide - Android.md at 2.1 · oovoodev/PrivateDocumentation</title>
    <link rel="search" type="application/opensearchdescription+xml" href="/opensearch.xml" title="GitHub">
    <link rel="fluid-icon" href="https://github.com/fluidicon.png" title="GitHub">
    <link rel="apple-touch-icon" sizes="57x57" href="/apple-touch-icon-114.png">
    <link rel="apple-touch-icon" sizes="114x114" href="/apple-touch-icon-114.png">
    <link rel="apple-touch-icon" sizes="72x72" href="/apple-touch-icon-144.png">
    <link rel="apple-touch-icon" sizes="144x144" href="/apple-touch-icon-144.png">
    <meta property="fb:app_id" content="1401488693436528">

      <meta content="@github" name="twitter:site" /><meta content="summary" name="twitter:card" /><meta content="oovoodev/PrivateDocumentation" name="twitter:title" /><meta content="Contribute to PrivateDocumentation development by creating an account on GitHub." name="twitter:description" /><meta content="https://avatars2.githubusercontent.com/u/5216747?v=3&amp;s=400" name="twitter:image:src" />
      <meta content="GitHub" property="og:site_name" /><meta content="object" property="og:type" /><meta content="https://avatars2.githubusercontent.com/u/5216747?v=3&amp;s=400" property="og:image" /><meta content="oovoodev/PrivateDocumentation" property="og:title" /><meta content="https://github.com/oovoodev/PrivateDocumentation" property="og:url" /><meta content="Contribute to PrivateDocumentation development by creating an account on GitHub." property="og:description" />
      <meta name="browser-stats-url" content="https://api.github.com/_private/browser/stats">
    <meta name="browser-errors-url" content="https://api.github.com/_private/browser/errors">
    <link rel="assets" href="https://assets-cdn.github.com/">
    <link rel="web-socket" href="wss://live.github.com/_sockets/MTAzNDU2NDo1ZWFhNjQ3Yzg4OTJjNGJjNTc2ZDVkOThlMTUwMDEwMjo4MDg1N2VlNzdiZDg3MWIwMWYyNjJhNDRkYWI3ZDcyYjU3NTg4M2IyZDE3ZDUzNDcwMGMxYzM5NjU4YjRkYTAz--f0fd31b1c5992f81548707bcac9e2b7e3e96ad10">
    <meta name="pjax-timeout" content="1000">
    <link rel="sudo-modal" href="/sessions/sudo_modal">

    <meta name="msapplication-TileImage" content="/windows-tile.png">
    <meta name="msapplication-TileColor" content="#ffffff">
    <meta name="selected-link" value="repo_source" data-pjax-transient>

    <meta name="google-site-verification" content="KT5gs8h0wvaagLKAVWq8bbeNwnZZK1r1XQysX3xurLU">
    <meta name="google-analytics" content="UA-3769691-2">

<meta content="collector.githubapp.com" name="octolytics-host" /><meta content="collector-cdn.github.com" name="octolytics-script-host" /><meta content="github" name="octolytics-app-id" /><meta content="C20191FD:07C6:EF9D11:56166F0D" name="octolytics-dimension-request_id" /><meta content="1034564" name="octolytics-actor-id" /><meta content="jaboutboul" name="octolytics-actor-login" /><meta content="756ebf657a17effb1373a49573b5e05f6d47287f19f253f16d48106aff0f4d10" name="octolytics-actor-hash" />
<meta content="/&lt;user-name&gt;/&lt;repo-name&gt;/blob/show" data-pjax-transient="true" name="analytics-location" />
<meta content="Rails, view, blob#show" data-pjax-transient="true" name="analytics-event" />


  <meta class="js-ga-set" name="dimension1" content="Logged In">
    <meta class="js-ga-set" name="dimension4" content="Current repo nav">




    <meta name="is-dotcom" content="true">
        <meta name="hostname" content="github.com">
    <meta name="user-login" content="jaboutboul">

      <link rel="mask-icon" href="https://assets-cdn.github.com/pinned-octocat.svg" color="#4078c0">
      <link rel="icon" type="image/x-icon" href="https://assets-cdn.github.com/favicon.ico">

      <!-- </textarea> --><!-- '"` --><meta content="authenticity_token" name="csrf-param" />
<meta content="D1Q2xHhDf2YbfsWnRTiwdCIvtASb5siT7HVDQ45+ZOJjUbuUvHXi+kw7EgKfc+m3xWgIpHRNXJPekZeYEOWA1w==" name="csrf-token" />
    <meta content="44948c3c688c9dec330ff41748d4bd0112153341" name="form-nonce" />

    <link crossorigin="anonymous" href="https://assets-cdn.github.com/assets/github-55fd156532d1d5fd0241b9062b86e446775b40baeb2e6390d3fc2c40ab2857d3.css" integrity="sha256-Vf0VZTLR1f0CQbkGK4bkRndbQLrrLmOQ0/wsQKsoV9M=" media="all" rel="stylesheet" />
    <link crossorigin="anonymous" href="https://assets-cdn.github.com/assets/github2-5fbd51630dd27a79b6107d38e57e4c6e8818d18b1d88f4df4bc3f145e211aa82.css" integrity="sha256-X71RYw3Senm2EH045X5MbogY0YsdiPTfS8PxReIRqoI=" media="all" rel="stylesheet" />
    
    
    


    <meta http-equiv="x-pjax-version" content="b77e81e67e61239409db763b02daffa5">

      
  <meta name="description" content="Contribute to PrivateDocumentation development by creating an account on GitHub.">
  <meta name="go-import" content="github.com/oovoodev/PrivateDocumentation git https://github.com/oovoodev/PrivateDocumentation.git">

  <meta content="5216747" name="octolytics-dimension-user_id" /><meta content="oovoodev" name="octolytics-dimension-user_login" /><meta content="43804259" name="octolytics-dimension-repository_id" /><meta content="oovoodev/PrivateDocumentation" name="octolytics-dimension-repository_nwo" /><meta content="false" name="octolytics-dimension-repository_public" /><meta content="false" name="octolytics-dimension-repository_is_fork" /><meta content="43804259" name="octolytics-dimension-repository_network_root_id" /><meta content="oovoodev/PrivateDocumentation" name="octolytics-dimension-repository_network_root_nwo" />
  <link href="https://github.com/oovoodev/PrivateDocumentation/commits/2.1.atom?token=AA_JRKTQ87R5sO3gfxLHextobffBVq02ks60I6-mwA%3D%3D" rel="alternate" title="Recent Commits to PrivateDocumentation:2.1" type="application/atom+xml">

  </head>


  <body class="logged_in   env-production macintosh vis-private page-blob">
    <a href="#start-of-content" tabindex="1" class="accessibility-aid js-skip-to-content">Skip to content</a>

    
    
    



      <div class="header header-logged-in true" role="banner">
  <div class="container clearfix">

    <a class="header-logo-invertocat" href="https://github.com/" data-hotkey="g d" aria-label="Homepage" data-ga-click="Header, go to dashboard, icon:logo">
  <span class="mega-octicon octicon-mark-github"></span>
</a>


      <div class="site-search repo-scope js-site-search" role="search">
          <!-- </textarea> --><!-- '"` --><form accept-charset="UTF-8" action="/oovoodev/PrivateDocumentation/search" class="js-site-search-form" data-global-search-url="/search" data-repo-search-url="/oovoodev/PrivateDocumentation/search" method="get"><div style="margin:0;padding:0;display:inline"><input name="utf8" type="hidden" value="&#x2713;" /></div>
  <label class="js-chromeless-input-container form-control">
    <div class="scope-badge">This repository</div>
    <input type="text"
      class="js-site-search-focus js-site-search-field is-clearable chromeless-input"
      data-hotkey="s"
      name="q"
      placeholder="Search"
      aria-label="Search this repository"
      data-global-scope-placeholder="Search GitHub"
      data-repo-scope-placeholder="Search"
      tabindex="1"
      autocapitalize="off">
  </label>
</form>
      </div>

      <ul class="header-nav left" role="navigation">
        <li class="header-nav-item">
          <a href="/pulls" class="js-selected-navigation-item header-nav-link" data-ga-click="Header, click, Nav menu - item:pulls context:user" data-hotkey="g p" data-selected-links="/pulls /pulls/assigned /pulls/mentioned /pulls">
            Pull requests
</a>        </li>
        <li class="header-nav-item">
          <a href="/issues" class="js-selected-navigation-item header-nav-link" data-ga-click="Header, click, Nav menu - item:issues context:user" data-hotkey="g i" data-selected-links="/issues /issues/assigned /issues/mentioned /issues">
            Issues
</a>        </li>
          <li class="header-nav-item">
            <a class="header-nav-link" href="https://gist.github.com/" data-ga-click="Header, go to gist, text:gist">Gist</a>
          </li>
      </ul>

    
<ul class="header-nav user-nav right" id="user-links">
  <li class="header-nav-item">
      <span class="js-socket-channel js-updatable-content"
        data-channel="notification-changed:jaboutboul"
        data-url="/notifications/header">
      <a href="/notifications" aria-label="You have unread notifications" class="header-nav-link notification-indicator tooltipped tooltipped-s" data-ga-click="Header, go to notifications, icon:unread" data-hotkey="g n">
          <span class="mail-status unread"></span>
          <span class="octicon octicon-bell"></span>
</a>  </span>

  </li>

  <li class="header-nav-item dropdown js-menu-container">
    <a class="header-nav-link tooltipped tooltipped-s js-menu-target" href="/new"
       aria-label="Create new…"
       data-ga-click="Header, create new, icon:add">
      <span class="octicon octicon-plus left"></span>
      <span class="dropdown-caret"></span>
    </a>

    <div class="dropdown-menu-content js-menu-content">
      <ul class="dropdown-menu dropdown-menu-sw">
        
<a class="dropdown-item" href="/new" data-ga-click="Header, create new repository">
  New repository
</a>


  <a class="dropdown-item" href="/organizations/new" data-ga-click="Header, create new organization">
    New organization
  </a>

  <div class="dropdown-divider"></div>
  <div class="dropdown-header">
    <span title="oovoodev">This organization</span>
  </div>
  <a class="dropdown-item" href="/orgs/oovoodev/invitations/new" data-ga-click="Header, invite someone">
    Invite someone
  </a>
  <a class="dropdown-item" href="/orgs/oovoodev/new-team" data-ga-click="Header, create new team">
    New team
  </a>
  <a class="dropdown-item" href="/organizations/oovoodev/repositories/new" data-ga-click="Header, create new organization repository, icon:repo">
    New repository
  </a>


  <div class="dropdown-divider"></div>
  <div class="dropdown-header">
    <span title="oovoodev/PrivateDocumentation">This repository</span>
  </div>
    <a class="dropdown-item" href="/oovoodev/PrivateDocumentation/issues/new" data-ga-click="Header, create new issue">
      New issue
    </a>
    <a class="dropdown-item" href="/oovoodev/PrivateDocumentation/settings/collaboration" data-ga-click="Header, create new collaborator">
      New collaborator
    </a>

      </ul>
    </div>
  </li>

  <li class="header-nav-item dropdown js-menu-container">
    <a class="header-nav-link name tooltipped tooltipped-s js-menu-target" href="/jaboutboul"
       aria-label="View profile and more"
       data-ga-click="Header, show menu, icon:avatar">
      <img alt="@jaboutboul" class="avatar" height="20" src="https://avatars2.githubusercontent.com/u/1034564?v=3&amp;s=40" width="20" />
      <span class="dropdown-caret"></span>
    </a>

    <div class="dropdown-menu-content js-menu-content">
      <div class="dropdown-menu  dropdown-menu-sw">
        <div class=" dropdown-header header-nav-current-user css-truncate">
            Signed in as <strong class="css-truncate-target">jaboutboul</strong>

        </div>


        <div class="dropdown-divider"></div>

          <a class="dropdown-item" href="/jaboutboul" data-ga-click="Header, go to profile, text:your profile">
            Your profile
          </a>
        <a class="dropdown-item" href="/stars" data-ga-click="Header, go to starred repos, text:your stars">
          Your stars
        </a>
        <a class="dropdown-item" href="/explore" data-ga-click="Header, go to explore, text:explore">
          Explore
        </a>
          <a class="dropdown-item" href="/integrations" data-ga-click="Header, go to integrations, text:integrations">
            Integrations
          </a>
        <a class="dropdown-item" href="https://help.github.com" data-ga-click="Header, go to help, text:help">
          Help
        </a>

          <div class="dropdown-divider"></div>

          <a class="dropdown-item" href="/settings/profile" data-ga-click="Header, go to settings, icon:settings">
            Settings
          </a>

          <!-- </textarea> --><!-- '"` --><form accept-charset="UTF-8" action="/logout" class="logout-form" data-form-nonce="44948c3c688c9dec330ff41748d4bd0112153341" method="post"><div style="margin:0;padding:0;display:inline"><input name="utf8" type="hidden" value="&#x2713;" /><input name="authenticity_token" type="hidden" value="zEIx2TRR4IAjAMcS6gnwG4JGzgLaDM0Ux7ecoLClDHHX/Xg4XGAiEoBguHrX0HE+I/X9xWNmkCHGQ/Pln3QANA==" /></div>
            <button class="dropdown-item dropdown-signout" data-ga-click="Header, sign out, icon:logout">
              Sign out
            </button>
</form>
      </div>
    </div>
  </li>
</ul>


    
  </div>
</div>

      

      


    <div id="start-of-content" class="accessibility-aid"></div>

    <div id="js-flash-container">
</div>


    <div role="main" class="main-content">
        <div itemscope itemtype="http://schema.org/WebPage">
    <div class="pagehead repohead instapaper_ignore readability-menu">

      <div class="container">

        <div class="clearfix">
          

<ul class="pagehead-actions">

  <li>
      <!-- </textarea> --><!-- '"` --><form accept-charset="UTF-8" action="/notifications/subscribe" class="js-social-container" data-autosubmit="true" data-form-nonce="44948c3c688c9dec330ff41748d4bd0112153341" data-remote="true" method="post"><div style="margin:0;padding:0;display:inline"><input name="utf8" type="hidden" value="&#x2713;" /><input name="authenticity_token" type="hidden" value="ocOUYQLvTdelA0hO1wQCO3D0asjVg3TaG/IlSLjUCPUKuy9PrJPbsHHckAOCdmv69VQJ25O2wpca7YJ1RPRURg==" /></div>    <input id="repository_id" name="repository_id" type="hidden" value="43804259" />

      <div class="select-menu js-menu-container js-select-menu">
        <a href="/oovoodev/PrivateDocumentation/subscription"
          class="btn btn-sm btn-with-count select-menu-button js-menu-target" role="button" tabindex="0" aria-haspopup="true"
          data-ga-click="Repository, click Watch settings, action:blob#show">
          <span class="js-select-button">
            <span class="octicon octicon-eye"></span>
            Unwatch
          </span>
        </a>
        <a class="social-count js-social-count" href="/oovoodev/PrivateDocumentation/watchers">
          7
        </a>

        <div class="select-menu-modal-holder">
          <div class="select-menu-modal subscription-menu-modal js-menu-content" aria-hidden="true">
            <div class="select-menu-header">
              <span class="select-menu-title">Notifications</span>
              <span class="octicon octicon-x js-menu-close" role="button" aria-label="Close"></span>
            </div>

            <div class="select-menu-list js-navigation-container" role="menu">

              <div class="select-menu-item js-navigation-item " role="menuitem" tabindex="0">
                <span class="select-menu-item-icon octicon octicon-check"></span>
                <div class="select-menu-item-text">
                  <input id="do_included" name="do" type="radio" value="included" />
                  <span class="select-menu-item-heading">Not watching</span>
                  <span class="description">Be notified when participating or @mentioned.</span>
                  <span class="js-select-button-text hidden-select-button-text">
                    <span class="octicon octicon-eye"></span>
                    Watch
                  </span>
                </div>
              </div>

              <div class="select-menu-item js-navigation-item selected" role="menuitem" tabindex="0">
                <span class="select-menu-item-icon octicon octicon octicon-check"></span>
                <div class="select-menu-item-text">
                  <input checked="checked" id="do_subscribed" name="do" type="radio" value="subscribed" />
                  <span class="select-menu-item-heading">Watching</span>
                  <span class="description">Be notified of all conversations.</span>
                  <span class="js-select-button-text hidden-select-button-text">
                    <span class="octicon octicon-eye"></span>
                    Unwatch
                  </span>
                </div>
              </div>

              <div class="select-menu-item js-navigation-item " role="menuitem" tabindex="0">
                <span class="select-menu-item-icon octicon octicon-check"></span>
                <div class="select-menu-item-text">
                  <input id="do_ignore" name="do" type="radio" value="ignore" />
                  <span class="select-menu-item-heading">Ignoring</span>
                  <span class="description">Never be notified.</span>
                  <span class="js-select-button-text hidden-select-button-text">
                    <span class="octicon octicon-mute"></span>
                    Stop ignoring
                  </span>
                </div>
              </div>

            </div>

          </div>
        </div>
      </div>
</form>
  </li>

  <li>
    
  <div class="js-toggler-container js-social-container starring-container ">

    <!-- </textarea> --><!-- '"` --><form accept-charset="UTF-8" action="/oovoodev/PrivateDocumentation/unstar" class="js-toggler-form starred js-unstar-button" data-form-nonce="44948c3c688c9dec330ff41748d4bd0112153341" data-remote="true" method="post"><div style="margin:0;padding:0;display:inline"><input name="utf8" type="hidden" value="&#x2713;" /><input name="authenticity_token" type="hidden" value="DPOrF24NTI+yXaNtcEOtLiy2q+p7LPTRjuF4hPKhFt1VpZ5BuPz2wT4uTO9r9ngh28mkfrHMveuLHBXrdf1QJg==" /></div>
      <button
        class="btn btn-sm btn-with-count js-toggler-target"
        aria-label="Unstar this repository" title="Unstar oovoodev/PrivateDocumentation"
        data-ga-click="Repository, click unstar button, action:blob#show; text:Unstar">
        <span class="octicon octicon-star"></span>
        Unstar
      </button>
        <a class="social-count js-social-count" href="/oovoodev/PrivateDocumentation/stargazers">
          0
        </a>
</form>
    <!-- </textarea> --><!-- '"` --><form accept-charset="UTF-8" action="/oovoodev/PrivateDocumentation/star" class="js-toggler-form unstarred js-star-button" data-form-nonce="44948c3c688c9dec330ff41748d4bd0112153341" data-remote="true" method="post"><div style="margin:0;padding:0;display:inline"><input name="utf8" type="hidden" value="&#x2713;" /><input name="authenticity_token" type="hidden" value="AECzVchdMmEtvRXJmntdTesK0DpIM1M0khj5dAIIZdwKS4n4L5FRL+TPQJ9ZQ4IyjTc9ImLU7dEan9Xkq5j8Kw==" /></div>
      <button
        class="btn btn-sm btn-with-count js-toggler-target"
        aria-label="Star this repository" title="Star oovoodev/PrivateDocumentation"
        data-ga-click="Repository, click star button, action:blob#show; text:Star">
        <span class="octicon octicon-star"></span>
        Star
      </button>
        <a class="social-count js-social-count" href="/oovoodev/PrivateDocumentation/stargazers">
          0
        </a>
</form>  </div>

  </li>

  <li>
          <a href="#fork-destination-box" class="btn btn-sm btn-with-count"
              title="Fork your own copy of oovoodev/PrivateDocumentation to your account"
              aria-label="Fork your own copy of oovoodev/PrivateDocumentation to your account"
              rel="facebox"
              data-ga-click="Repository, show fork modal, action:blob#show; text:Fork">
            <span class="octicon octicon-repo-forked"></span>
            Fork
          </a>

          <div id="fork-destination-box" style="display: none;">
            <h2 class="facebox-header" data-facebox-id="facebox-header">Where should we fork this repository?</h2>
            <include-fragment src=""
                class="js-fork-select-fragment fork-select-fragment"
                data-url="/oovoodev/PrivateDocumentation/fork?fragment=1">
              <img alt="Loading" height="64" src="https://assets-cdn.github.com/images/spinners/octocat-spinner-128.gif" width="64" />
            </include-fragment>
          </div>

    <a href="/oovoodev/PrivateDocumentation/network" class="social-count">
      0
    </a>
  </li>
</ul>

          <h1 itemscope itemtype="http://data-vocabulary.org/Breadcrumb" class="entry-title private ">
  <span class="mega-octicon octicon-lock"></span>
  <span class="author"><a href="/oovoodev" class="url fn" itemprop="url" rel="author"><span itemprop="title">oovoodev</span></a></span><!--
--><span class="path-divider">/</span><!--
--><strong><a href="/oovoodev/PrivateDocumentation" data-pjax="#js-repo-pjax-container">PrivateDocumentation</a></strong>
    <span class="repo-private-label">private</span>

  <span class="page-context-loader">
    <img alt="" height="16" src="https://assets-cdn.github.com/images/spinners/octocat-spinner-32.gif" width="16" />
  </span>

</h1>

        </div>
      </div>
    </div>

    <div class="container">
      <div class="repository-with-sidebar repo-container new-discussion-timeline ">
        <div class="repository-sidebar clearfix">
          
<nav class="sunken-menu repo-nav js-repo-nav js-sidenav-container-pjax js-octicon-loaders"
     role="navigation"
     data-pjax="#js-repo-pjax-container"
     data-issue-count-url="/oovoodev/PrivateDocumentation/issues/counts">
  <ul class="sunken-menu-group">
    <li class="tooltipped tooltipped-w" aria-label="Code">
      <a href="/oovoodev/PrivateDocumentation/tree/2.1" aria-label="Code" aria-selected="true" class="js-selected-navigation-item selected sunken-menu-item" data-hotkey="g c" data-selected-links="repo_source repo_downloads repo_commits repo_releases repo_tags repo_branches /oovoodev/PrivateDocumentation/tree/2.1">
        <span class="octicon octicon-code"></span> <span class="full-word">Code</span>
        <img alt="" class="mini-loader" height="16" src="https://assets-cdn.github.com/images/spinners/octocat-spinner-32.gif" width="16" />
</a>    </li>

      <li class="tooltipped tooltipped-w" aria-label="Issues">
        <a href="/oovoodev/PrivateDocumentation/issues" aria-label="Issues" class="js-selected-navigation-item sunken-menu-item" data-hotkey="g i" data-selected-links="repo_issues repo_labels repo_milestones /oovoodev/PrivateDocumentation/issues">
          <span class="octicon octicon-issue-opened"></span> <span class="full-word">Issues</span>
          <span class="js-issue-replace-counter"></span>
          <img alt="" class="mini-loader" height="16" src="https://assets-cdn.github.com/images/spinners/octocat-spinner-32.gif" width="16" />
</a>      </li>

    <li class="tooltipped tooltipped-w" aria-label="Pull requests">
      <a href="/oovoodev/PrivateDocumentation/pulls" aria-label="Pull requests" class="js-selected-navigation-item sunken-menu-item" data-hotkey="g p" data-selected-links="repo_pulls /oovoodev/PrivateDocumentation/pulls">
          <span class="octicon octicon-git-pull-request"></span> <span class="full-word">Pull requests</span>
          <span class="js-pull-replace-counter"></span>
          <img alt="" class="mini-loader" height="16" src="https://assets-cdn.github.com/images/spinners/octocat-spinner-32.gif" width="16" />
</a>    </li>

      <li class="tooltipped tooltipped-w" aria-label="Wiki">
        <a href="/oovoodev/PrivateDocumentation/wiki" aria-label="Wiki" class="js-selected-navigation-item sunken-menu-item" data-hotkey="g w" data-selected-links="repo_wiki /oovoodev/PrivateDocumentation/wiki">
          <span class="octicon octicon-book"></span> <span class="full-word">Wiki</span>
          <img alt="" class="mini-loader" height="16" src="https://assets-cdn.github.com/images/spinners/octocat-spinner-32.gif" width="16" />
</a>      </li>
  </ul>
  <div class="sunken-menu-separator"></div>
  <ul class="sunken-menu-group">

    <li class="tooltipped tooltipped-w" aria-label="Pulse">
      <a href="/oovoodev/PrivateDocumentation/pulse" aria-label="Pulse" class="js-selected-navigation-item sunken-menu-item" data-selected-links="pulse /oovoodev/PrivateDocumentation/pulse">
        <span class="octicon octicon-pulse"></span> <span class="full-word">Pulse</span>
        <img alt="" class="mini-loader" height="16" src="https://assets-cdn.github.com/images/spinners/octocat-spinner-32.gif" width="16" />
</a>    </li>

    <li class="tooltipped tooltipped-w" aria-label="Graphs">
      <a href="/oovoodev/PrivateDocumentation/graphs" aria-label="Graphs" class="js-selected-navigation-item sunken-menu-item" data-selected-links="repo_graphs repo_contributors /oovoodev/PrivateDocumentation/graphs">
        <span class="octicon octicon-graph"></span> <span class="full-word">Graphs</span>
        <img alt="" class="mini-loader" height="16" src="https://assets-cdn.github.com/images/spinners/octocat-spinner-32.gif" width="16" />
</a>    </li>
  </ul>


    <div class="sunken-menu-separator"></div>
    <ul class="sunken-menu-group">
      <li class="tooltipped tooltipped-w" aria-label="Settings">
        <a href="/oovoodev/PrivateDocumentation/settings" aria-label="Settings" class="js-selected-navigation-item sunken-menu-item" data-selected-links="repo_settings repo_branch_settings hooks /oovoodev/PrivateDocumentation/settings">
          <span class="octicon octicon-gear"></span> <span class="full-word">Settings</span>
          <img alt="" class="mini-loader" height="16" src="https://assets-cdn.github.com/images/spinners/octocat-spinner-32.gif" width="16" />
</a>      </li>
    </ul>
</nav>

            <div class="only-with-full-nav">
                
<div class="js-clone-url clone-url open"
  data-protocol-type="http">
  <h3 class="text-small"><span class="text-emphasized">HTTPS</span> clone URL</h3>
  <div class="input-group js-zeroclipboard-container">
    <input type="text" class="input-mini text-small input-monospace js-url-field js-zeroclipboard-target"
           value="https://github.com/oovoodev/PrivateDocumentation.git" readonly="readonly" aria-label="HTTPS clone URL">
    <span class="input-group-button">
      <button aria-label="Copy to clipboard" class="js-zeroclipboard btn btn-sm zeroclipboard-button tooltipped tooltipped-s" data-copied-hint="Copied!" type="button"><span class="octicon octicon-clippy"></span></button>
    </span>
  </div>
</div>

  
<div class="js-clone-url clone-url "
  data-protocol-type="ssh">
  <h3 class="text-small"><span class="text-emphasized">SSH</span> clone URL</h3>
  <div class="input-group js-zeroclipboard-container">
    <input type="text" class="input-mini text-small input-monospace js-url-field js-zeroclipboard-target"
           value="git@github.com:oovoodev/PrivateDocumentation.git" readonly="readonly" aria-label="SSH clone URL">
    <span class="input-group-button">
      <button aria-label="Copy to clipboard" class="js-zeroclipboard btn btn-sm zeroclipboard-button tooltipped tooltipped-s" data-copied-hint="Copied!" type="button"><span class="octicon octicon-clippy"></span></button>
    </span>
  </div>
</div>

  
<div class="js-clone-url clone-url "
  data-protocol-type="subversion">
  <h3 class="text-small"><span class="text-emphasized">Subversion</span> checkout URL</h3>
  <div class="input-group js-zeroclipboard-container">
    <input type="text" class="input-mini text-small input-monospace js-url-field js-zeroclipboard-target"
           value="https://github.com/oovoodev/PrivateDocumentation" readonly="readonly" aria-label="Subversion checkout URL">
    <span class="input-group-button">
      <button aria-label="Copy to clipboard" class="js-zeroclipboard btn btn-sm zeroclipboard-button tooltipped tooltipped-s" data-copied-hint="Copied!" type="button"><span class="octicon octicon-clippy"></span></button>
    </span>
  </div>
</div>



<div class="clone-options text-small">You can clone with
  <!-- </textarea> --><!-- '"` --><form accept-charset="UTF-8" action="/users/set_protocol?protocol_selector=http&amp;protocol_type=push" class="inline-form js-clone-selector-form is-enabled" data-form-nonce="44948c3c688c9dec330ff41748d4bd0112153341" data-remote="true" method="post"><div style="margin:0;padding:0;display:inline"><input name="utf8" type="hidden" value="&#x2713;" /><input name="authenticity_token" type="hidden" value="L6euViPmROLteRi15mJOMElPBpyozrgeBUzsE509B3WgQFGHhYymfE2NamieTLTEQZ5nSNHQ1osVvKXh0aySMQ==" /></div><button class="btn-link js-clone-selector" data-protocol="http" type="submit">HTTPS</button></form>, <!-- </textarea> --><!-- '"` --><form accept-charset="UTF-8" action="/users/set_protocol?protocol_selector=ssh&amp;protocol_type=push" class="inline-form js-clone-selector-form is-enabled" data-form-nonce="44948c3c688c9dec330ff41748d4bd0112153341" data-remote="true" method="post"><div style="margin:0;padding:0;display:inline"><input name="utf8" type="hidden" value="&#x2713;" /><input name="authenticity_token" type="hidden" value="9ADhPn/fjgoDlJxsNSHamweG11TR5lg91wEieD4RIFv+hK1tiQi6Nc2Nw6D4eA/8e7XtXi/zjx7Il3bqKwOtaw==" /></div><button class="btn-link js-clone-selector" data-protocol="ssh" type="submit">SSH</button></form>, or <!-- </textarea> --><!-- '"` --><form accept-charset="UTF-8" action="/users/set_protocol?protocol_selector=subversion&amp;protocol_type=push" class="inline-form js-clone-selector-form is-enabled" data-form-nonce="44948c3c688c9dec330ff41748d4bd0112153341" data-remote="true" method="post"><div style="margin:0;padding:0;display:inline"><input name="utf8" type="hidden" value="&#x2713;" /><input name="authenticity_token" type="hidden" value="vKJzA+UrWIHK1BwGPJeHjZT89gH2YiRc1EcKx5YB/A3GBi2a9NnC8/0xT7qFOazti4XQ8Q3zhZN5v83TfgzYCg==" /></div><button class="btn-link js-clone-selector" data-protocol="subversion" type="submit">Subversion</button></form>.
  <a href="https://help.github.com/articles/which-remote-url-should-i-use" class="help tooltipped tooltipped-n" aria-label="Get help on which URL is right for you.">
    <span class="octicon octicon-question"></span>
  </a>
</div>
  <a href="github-mac://openRepo/https://github.com/oovoodev/PrivateDocumentation" class="btn btn-sm sidebar-button" title="Save oovoodev/PrivateDocumentation to your computer and use it in GitHub Desktop." aria-label="Save oovoodev/PrivateDocumentation to your computer and use it in GitHub Desktop.">
    <span class="octicon octicon-desktop-download"></span>
    Clone in Desktop
  </a>

              <a href="/oovoodev/PrivateDocumentation/archive/2.1.zip"
                 class="btn btn-sm sidebar-button"
                 aria-label="Download the contents of oovoodev/PrivateDocumentation as a zip file"
                 title="Download the contents of oovoodev/PrivateDocumentation as a zip file"
                 rel="nofollow">
                <span class="octicon octicon-cloud-download"></span>
                Download ZIP
              </a>
            </div>
        </div>
        <div id="js-repo-pjax-container" class="repository-content context-loader-container" data-pjax-container>

          

<a href="/oovoodev/PrivateDocumentation/blob/6b8aec81051cdcbe2346e042f1cefcbe43757f24/Android%20Documentation/API%20Guide%20-%20Android.md" class="hidden js-permalink-shortcut" data-hotkey="y">Permalink</a>

<!-- blob contrib key: blob_contributors:v21:71326639a94dc1660ede8e0a51a3c322 -->

  <div class="file-navigation js-zeroclipboard-container">
    
<div class="select-menu js-menu-container js-select-menu left">
  <span class="btn btn-sm select-menu-button js-menu-target css-truncate" data-hotkey="w"
    title="2.1"
    role="button" aria-label="Switch branches or tags" tabindex="0" aria-haspopup="true">
    <i>Branch:</i>
    <span class="js-select-button css-truncate-target">2.1</span>
  </span>

  <div class="select-menu-modal-holder js-menu-content js-navigation-container" data-pjax aria-hidden="true">

    <div class="select-menu-modal">
      <div class="select-menu-header">
        <span class="select-menu-title">Switch branches/tags</span>
        <span class="octicon octicon-x js-menu-close" role="button" aria-label="Close"></span>
      </div>

      <div class="select-menu-filters">
        <div class="select-menu-text-filter">
          <input type="text" aria-label="Find or create a branch…" id="context-commitish-filter-field" class="js-filterable-field js-navigation-enable" placeholder="Find or create a branch…">
        </div>
        <div class="select-menu-tabs">
          <ul>
            <li class="select-menu-tab">
              <a href="#" data-tab-filter="branches" data-filter-placeholder="Find or create a branch…" class="js-select-menu-tab" role="tab">Branches</a>
            </li>
            <li class="select-menu-tab">
              <a href="#" data-tab-filter="tags" data-filter-placeholder="Find a tag…" class="js-select-menu-tab" role="tab">Tags</a>
            </li>
          </ul>
        </div>
      </div>

      <div class="select-menu-list select-menu-tab-bucket js-select-menu-tab-bucket" data-tab-filter="branches" role="menu">

        <div data-filterable-for="context-commitish-filter-field" data-filterable-type="substring">


            <a class="select-menu-item js-navigation-item js-navigation-open "
               href="/oovoodev/PrivateDocumentation/blob/2.0/Android%20Documentation/API%20Guide%20-%20Android.md"
               data-name="2.0"
               data-skip-pjax="true"
               rel="nofollow">
              <span class="select-menu-item-icon octicon octicon-check"></span>
              <span class="select-menu-item-text css-truncate-target" title="2.0">
                2.0
              </span>
            </a>
            <a class="select-menu-item js-navigation-item js-navigation-open selected"
               href="/oovoodev/PrivateDocumentation/blob/2.1/Android%20Documentation/API%20Guide%20-%20Android.md"
               data-name="2.1"
               data-skip-pjax="true"
               rel="nofollow">
              <span class="select-menu-item-icon octicon octicon-check"></span>
              <span class="select-menu-item-text css-truncate-target" title="2.1">
                2.1
              </span>
            </a>
            <a class="select-menu-item js-navigation-item js-navigation-open "
               href="/oovoodev/PrivateDocumentation/blob/2.2/Android%20Documentation/API%20Guide%20-%20Android.md"
               data-name="2.2"
               data-skip-pjax="true"
               rel="nofollow">
              <span class="select-menu-item-icon octicon octicon-check"></span>
              <span class="select-menu-item-text css-truncate-target" title="2.2">
                2.2
              </span>
            </a>
        </div>

          <!-- </textarea> --><!-- '"` --><form accept-charset="UTF-8" action="/oovoodev/PrivateDocumentation/branches" class="js-create-branch select-menu-item select-menu-new-item-form js-navigation-item js-new-item-form" data-form-nonce="44948c3c688c9dec330ff41748d4bd0112153341" method="post"><div style="margin:0;padding:0;display:inline"><input name="utf8" type="hidden" value="&#x2713;" /><input name="authenticity_token" type="hidden" value="xPbHSTKi0mw9l7XPBUVET/8OWzhNq7dip0qOK3wiUJ27zjPjScfMbCXEscOT43gqSDM5mxA7Y9Noy0FT6nx7kQ==" /></div>
            <span class="octicon octicon-git-branch select-menu-item-icon"></span>
            <div class="select-menu-item-text">
              <span class="select-menu-item-heading">Create branch: <span class="js-new-item-name"></span></span>
              <span class="description">from ‘2.1’</span>
            </div>
            <input type="hidden" name="name" id="name" class="js-new-item-value">
            <input type="hidden" name="branch" id="branch" value="2.1">
            <input type="hidden" name="path" id="path" value="Android Documentation/API Guide - Android.md">
</form>
      </div>

      <div class="select-menu-list select-menu-tab-bucket js-select-menu-tab-bucket" data-tab-filter="tags">
        <div data-filterable-for="context-commitish-filter-field" data-filterable-type="substring">


        </div>

        <div class="select-menu-no-results">Nothing to show</div>
      </div>

    </div>
  </div>
</div>

    <div class="btn-group right">
      <a href="/oovoodev/PrivateDocumentation/find/2.1"
            class="js-show-file-finder btn btn-sm empty-icon tooltipped tooltipped-nw"
            data-pjax
            data-hotkey="t"
            aria-label="Quickly jump between files">
        <span class="octicon octicon-list-unordered"></span>
      </a>
      <button aria-label="Copy file path to clipboard" class="js-zeroclipboard btn btn-sm zeroclipboard-button tooltipped tooltipped-s" data-copied-hint="Copied!" type="button"><span class="octicon octicon-clippy"></span></button>
    </div>

    <div class="breadcrumb js-zeroclipboard-target">
      <span class="repo-root js-repo-root"><span itemscope="" itemtype="http://data-vocabulary.org/Breadcrumb"><a href="/oovoodev/PrivateDocumentation/tree/2.1" class="" data-branch="2.1" data-pjax="true" itemscope="url"><span itemprop="title">PrivateDocumentation</span></a></span></span><span class="separator">/</span><span itemscope="" itemtype="http://data-vocabulary.org/Breadcrumb"><a href="/oovoodev/PrivateDocumentation/tree/2.1/Android%20Documentation" class="" data-branch="2.1" data-pjax="true" itemscope="url"><span itemprop="title">Android Documentation</span></a></span><span class="separator">/</span><strong class="final-path">API Guide - Android.md</strong>
    </div>
  </div>


  <div class="commit file-history-tease">
    <div class="file-history-tease-header">
        <img alt="@abalasanov" class="avatar" height="24" src="https://avatars0.githubusercontent.com/u/9657116?v=3&amp;s=48" width="24" />
        <span class="author"><a href="/abalasanov" rel="contributor">abalasanov</a></span>
        <time datetime="2015-10-08T11:45:19Z" is="relative-time">Oct 8, 2015</time>
        <div class="commit-title">
            <a href="/oovoodev/PrivateDocumentation/commit/e93419dd3d04d0af1fa92d69ffd1d65ee9bcceed" class="message" data-pjax="true" title="Add changes for send to sendData, android guide">Add changes for send to sendData, android guide</a>
        </div>
    </div>

    <div class="participation">
      <p class="quickstat">
        <a href="#blob_contributors_box" rel="facebox">
          <strong>5</strong>
           contributors
        </a>
      </p>
          <a class="avatar-link tooltipped tooltipped-s" aria-label="SashaKalgin" href="/oovoodev/PrivateDocumentation/commits/2.2/Android%20Documentation/API%20Guide%20-%20Android.md?author=SashaKalgin"><img alt="@SashaKalgin" class="avatar" height="20" src="https://avatars3.githubusercontent.com/u/12987789?v=3&amp;s=40" width="20" /> </a>
    <a class="avatar-link tooltipped tooltipped-s" aria-label="eranmalovany" href="/oovoodev/PrivateDocumentation/commits/2.2/Android%20Documentation/API%20Guide%20-%20Android.md?author=eranmalovany"><img alt="@eranmalovany" class="avatar" height="20" src="https://avatars1.githubusercontent.com/u/3629370?v=3&amp;s=40" width="20" /> </a>
    <a class="avatar-link tooltipped tooltipped-s" aria-label="eakraly" href="/oovoodev/PrivateDocumentation/commits/2.2/Android%20Documentation/API%20Guide%20-%20Android.md?author=eakraly"><img alt="@eakraly" class="avatar" height="20" src="https://avatars1.githubusercontent.com/u/2505440?v=3&amp;s=40" width="20" /> </a>
    <a class="avatar-link tooltipped tooltipped-s" aria-label="jaboutboul" href="/oovoodev/PrivateDocumentation/commits/2.2/Android%20Documentation/API%20Guide%20-%20Android.md?author=jaboutboul"><img alt="@jaboutboul" class="avatar" height="20" src="https://avatars2.githubusercontent.com/u/1034564?v=3&amp;s=40" width="20" /> </a>
    <a class="avatar-link tooltipped tooltipped-s" aria-label="abalasanov" href="/oovoodev/PrivateDocumentation/commits/2.2/Android%20Documentation/API%20Guide%20-%20Android.md?author=abalasanov"><img alt="@abalasanov" class="avatar" height="20" src="https://avatars2.githubusercontent.com/u/9657116?v=3&amp;s=40" width="20" /> </a>


    </div>
    <div id="blob_contributors_box" style="display:none">
      <h2 class="facebox-header" data-facebox-id="facebox-header">Users who have contributed to this file</h2>
      <ul class="facebox-user-list" data-facebox-id="facebox-description">
          <li class="facebox-user-list-item">
            <img alt="@SashaKalgin" height="24" src="https://avatars1.githubusercontent.com/u/12987789?v=3&amp;s=48" width="24" />
            <a href="/SashaKalgin">SashaKalgin</a>
          </li>
          <li class="facebox-user-list-item">
            <img alt="@eranmalovany" height="24" src="https://avatars3.githubusercontent.com/u/3629370?v=3&amp;s=48" width="24" />
            <a href="/eranmalovany">eranmalovany</a>
          </li>
          <li class="facebox-user-list-item">
            <img alt="@eakraly" height="24" src="https://avatars3.githubusercontent.com/u/2505440?v=3&amp;s=48" width="24" />
            <a href="/eakraly">eakraly</a>
          </li>
          <li class="facebox-user-list-item">
            <img alt="@jaboutboul" height="24" src="https://avatars0.githubusercontent.com/u/1034564?v=3&amp;s=48" width="24" />
            <a href="/jaboutboul">jaboutboul</a>
          </li>
          <li class="facebox-user-list-item">
            <img alt="@abalasanov" height="24" src="https://avatars0.githubusercontent.com/u/9657116?v=3&amp;s=48" width="24" />
            <a href="/abalasanov">abalasanov</a>
          </li>
      </ul>
    </div>
  </div>

<div class="file">
  <div class="file-header">
  <div class="file-actions">

    <div class="btn-group">
      <a href="/oovoodev/PrivateDocumentation/raw/2.1/Android%20Documentation/API%20Guide%20-%20Android.md" class="btn btn-sm " id="raw-url">Raw</a>
        <a href="/oovoodev/PrivateDocumentation/blame/2.1/Android%20Documentation/API%20Guide%20-%20Android.md" class="btn btn-sm js-update-url-with-hash">Blame</a>
      <a href="/oovoodev/PrivateDocumentation/commits/2.1/Android%20Documentation/API%20Guide%20-%20Android.md" class="btn btn-sm " rel="nofollow">History</a>
    </div>

      <a class="octicon-btn tooltipped tooltipped-nw"
         href="github-mac://openRepo/https://github.com/oovoodev/PrivateDocumentation?branch=2.1&amp;filepath=Android%20Documentation%2FAPI%20Guide%20-%20Android.md"
         aria-label="Open this file in GitHub Desktop"
         data-ga-click="Repository, open with desktop, type:mac">
          <span class="octicon octicon-device-desktop"></span>
      </a>

        <!-- </textarea> --><!-- '"` --><form accept-charset="UTF-8" action="/oovoodev/PrivateDocumentation/edit/2.1/Android%20Documentation/API%20Guide%20-%20Android.md" class="inline-form js-update-url-with-hash" data-form-nonce="44948c3c688c9dec330ff41748d4bd0112153341" method="post"><div style="margin:0;padding:0;display:inline"><input name="utf8" type="hidden" value="&#x2713;" /><input name="authenticity_token" type="hidden" value="WHlitasZa63Q1A6+bNVzm9AXwDiewi0wpKXmw2ihXUFxTsWsnIA2mRXIqUc2a2HEVQkdEXVa1E16zrKLUx69yg==" /></div>
          <button class="octicon-btn tooltipped tooltipped-nw" type="submit"
            aria-label="Edit this file" data-hotkey="e" data-disable-with>
            <span class="octicon octicon-pencil"></span>
          </button>
</form>        <!-- </textarea> --><!-- '"` --><form accept-charset="UTF-8" action="/oovoodev/PrivateDocumentation/delete/2.1/Android%20Documentation/API%20Guide%20-%20Android.md" class="inline-form" data-form-nonce="44948c3c688c9dec330ff41748d4bd0112153341" method="post"><div style="margin:0;padding:0;display:inline"><input name="utf8" type="hidden" value="&#x2713;" /><input name="authenticity_token" type="hidden" value="TFD2T9TAk6s+Ed8rdDDZZrTVjYlRK/cEX/6heL4ihDtPihfEjfKzPPqBCgtkn6X7ZIWfqi8VuLOyJTbcdwpiMg==" /></div>
          <button class="octicon-btn octicon-btn-danger tooltipped tooltipped-nw" type="submit"
            aria-label="Delete this file" data-disable-with>
            <span class="octicon octicon-trashcan"></span>
          </button>
</form>  </div>

  <div class="file-info">
      1611 lines (1070 sloc)
      <span class="file-info-divider"></span>
    46.7 KB
  </div>
</div>

  
  <div id="readme" class="blob instapaper_body">
    <article class="markdown-body entry-content" itemprop="mainContentOfPage"><h1><a id="user-content-android-api-guide" class="anchor" href="#android-api-guide" aria-hidden="true"><span class="octicon octicon-link"></span></a>Android API Guide</h1>

<p>Table of Contents</p>



<ul>
<li><a href="#android-api-guide">Android API Guide</a></li>
<li><a href="#classes">Classes</a></li>
<li><a href="#oovooclient">ooVooClient</a>

<ul>
<li><a href="#constructor">Constructor</a></li>
<li><a href="#sharedinstance">sharedInstance</a></li>
<li><a href="#getaccount">getAccount</a></li>
<li><a href="#getavchat">getAVChat</a></li>
<li><a href="#isauthorized">isAuthorized</a></li>
<li><a href="#isdevicesupported">isDeviceSupported</a></li>
<li><a href="#setcontext">setContext</a></li>
<li><a href="#istablet">isTablet</a></li>
<li><a href="#setsslpeerverify">setSslPeerVerify</a></li>
<li><a href="#issslpeerverify">isSslPeerVerify</a></li>
<li><a href="#authorizeclient">authorizeClient</a></li>
<li><a href="#setlogger">setLogger</a></li>
<li><a href="#setloglevel">setLogLevel</a></li>
<li><a href="#getsdkversion">getSdkVersion</a></li>
<li><a href="#updateconfig">updateConfig</a></li>
</ul></li>
<li><a href="#jniobject">JNIObject</a>

<ul>
<li><a href="#isvalid">isValid</a></li>
<li><a href="#release">release</a></li>
</ul></li>
<li><a href="#account">Account</a>

<ul>
<li><a href="#login">login</a></li>
<li><a href="#getid">getID</a></li>
<li><a href="#logout">logout</a></li>
</ul></li>
<li><a href="#device">Device</a>

<ul>
<li><a href="#getid">getID</a></li>
<li><a href="#getname">getName</a></li>
</ul></li>
<li><a href="#effect">Effect</a>

<ul>
<li><a href="#getcategory">getCategory</a></li>
<li><a href="#geticonurl">getIconUrl</a></li>
<li><a href="#getid">getID</a></li>
<li><a href="#getname">getName</a></li>
<li><a href="#getpurchaseid">getPurchaseId</a></li>
</ul></li>
<li><a href="#pluginfactory">PluginFactory</a>

<ul>
<li><a href="#createplugininstance">createPluginInstance</a></li>
</ul></li>
<li><a href="#oovoosdkresultlistener">ooVooSdkResultListener</a>

<ul>
<li><a href="#onresult">onResult</a></li>
</ul></li>
<li><a href="#oovoosdkresult">ooVooSdkResult</a>

<ul>
<li><a href="#getresult">getResult</a></li>
<li><a href="#getdescription">getDescription</a></li>
<li><a href="#getuserinfo">getUserInfo</a></li>
</ul></li>
<li><a href="#loggerlistener">LoggerListener</a>

<ul>
<li><a href="#loglevel">LogLevel</a></li>
<li><a href="#fromint">fromInt</a></li>
<li><a href="#leveltoint">levelToInt</a></li>
<li><a href="#fromstring">fromString</a></li>
<li><a href="#onlog">OnLog</a></li>
</ul></li>
<li><a href="#avchat">AVChat</a>

<ul>
<li><a href="#conferencestate">ConferenceState</a></li>
<li><a href="#setlistener">setListener</a></li>
<li><a href="#join">join</a></li>
<li><a href="#leave">leave</a></li>
<li><a href="#senddata">sendData</a></li>
<li><a href="#senddata">sendData</a></li>
<li><a href="#registerplugin">registerPlugin</a></li>
<li><a href="#unregisterplugin">unregisterPlugin</a></li>
<li><a href="#isincallmessagespermit">isInCallMessagesPermit</a></li>
<li><a href="#getavailableresolutions">getAvailableResolutions</a></li>
<li><a href="#isresolutionsupported">isResolutionSupported</a></li>
<li><a href="#getvideocontroller">getVideoController</a></li>
<li><a href="#getaudiocontroller">getAudioController</a></li>
<li><a href="#avchatlistener">AVChatListener</a>

<ul>
<li><a href="#onparticipantjoined">onParticipantJoined</a></li>
<li><a href="#onparticipantleft">onParticipantLeft</a></li>
<li><a href="#onconferencestatechanged">onConferenceStateChanged</a></li>
<li><a href="#onreceivedata">onReceiveData</a></li>
<li><a href="#onconferenceerror">onConferenceError</a></li>
<li><a href="#onnetworkreliability">onNetworkReliability</a></li>
</ul></li>
</ul></li>
<li><a href="#participant">Participant</a>

<ul>
<li><a href="#participanttype">ParticipantType</a></li>
<li><a href="#getid">getID</a></li>
<li><a href="#gettype">getType</a></li>
</ul></li>
<li><a href="#audiocontroller">AudioController</a>

<ul>
<li><a href="#audioroutemode">AudioRouteMode</a></li>
<li><a href="#setlistener">setListener</a></li>
<li><a href="#initaudio">initAudio</a></li>
<li><a href="#uninitaudio">uninitAudio</a></li>
<li><a href="#isplaybackmuted">isPlaybackMuted</a></li>
<li><a href="#isrecordmuted">isRecordMuted</a></li>
<li><a href="#setrecordmuted">setRecordMuted</a></li>
<li><a href="#setplaybackmuted">setPlaybackMuted</a></li>
<li><a href="#getaudioroutecontroller">getAudioRouteController</a></li>
<li><a href="#setaudioroutemode">setAudioRouteMode</a></li>
<li><a href="#audiocontrollerlistener">AudioControllerListener</a>

<ul>
<li><a href="#onaudiotransmitstatechanged">onAudioTransmitStateChanged</a></li>
<li><a href="#onaudioreceivestatechanged">onAudioReceiveStateChanged</a></li>
<li><a href="#onmicrophonestatechange">onMicrophoneStateChange</a></li>
<li><a href="#onspeakerstatechange">onSpeakerStateChange</a></li>
</ul></li>
</ul></li>
<li><a href="#audioroute">AudioRoute</a>

<ul>
<li><a href="#getname">getName</a></li>
<li><a href="#getrouteid">getRouteId</a></li>
<li><a href="#isactive">isActive</a></li>
</ul></li>
<li><a href="#audioroutecontroller">AudioRouteController</a>

<ul>
<li><a href="#getroutes">getRoutes</a></li>
<li><a href="#setlistener">setListener</a></li>
<li><a href="#setRoute">setRoute</a></li>
<li><a href="#audioroutecontrollerlistener">AudioRouteControllerListener</a>

<ul>
<li><a href="#onaudioroutechanged">onAudioRouteChanged</a></li>
</ul></li>
</ul></li>
<li><a href="#videocontroller">VideoController</a>

<ul>
<li><a href="#resolutionlevel">ResolutionLevel</a></li>
<li><a href="#videoconfigkey">VideoConfigKey</a></li>
<li><a href="#getconfig">getConfig</a></li>
<li><a href="#setconfig">setConfig</a></li>
<li><a href="#setlistener">setListener</a></li>
<li><a href="#setactiveresolution">setActiveResolution</a></li>
<li><a href="#getactiveresolution">getActiveResolution</a></li>
<li><a href="#setfps">setFps</a></li>
<li><a href="#getfps">getFps</a></li>
<li><a href="#setactiveeffect">setActiveEffect</a></li>
<li><a href="#getactiveeffect">getActiveEffect</a></li>
<li><a href="#setactivedevice">setActiveDevice</a></li>
<li><a href="#getactivedevice">getActiveDevice</a></li>
<li><a href="#openpreview">openPreview</a></li>
<li><a href="#closepreview">closePreview</a></li>
<li><a href="#opencamera">openCamera</a></li>
<li><a href="#closecamera">closeCamera</a></li>
<li><a href="#starttransmit">startTransmit</a></li>
<li><a href="#stoptransmit">stopTransmit</a></li>
<li><a href="#istransmited">isTransmited</a></li>
<li><a href="#bindrender">bindRender</a></li>
<li><a href="#unbindrender">unbindRender</a></li>
<li><a href="#registerremote">registerRemote</a></li>
<li><a href="#unregisterremote">unregisterRemote</a></li>
<li><a href="#getdevicelist">getDeviceList</a></li>
<li><a href="#geteffectlist">getEffectList</a></li>
<li><a href="#sizetoresolutionlevel">sizeToResolutionLevel</a></li>
<li><a href="#videocontrollerlistener">VideoControllerListener</a>

<ul>
<li><a href="#remotevideostate">RemoteVideoState</a></li>
<li><a href="#onremotevideostatechanged">onRemoteVideoStateChanged</a></li>
<li><a href="#oncamerastatechanged">onCameraStateChanged</a></li>
<li><a href="#ontransmitstatechanged">onTransmitStateChanged</a></li>
<li><a href="#onvideopreviewstatechanged">onVideoPreviewStateChanged</a></li>
<li><a href="#oncamerachanged">onCameraChanged</a></li>
</ul></li>
</ul></li>
<li><a href="#videodevice">VideoDevice</a>

<ul>
<li><a href="#getavailableresolutions">getAvailableResolutions</a></li>
<li><a href="#isresolutionsupported">isResolutionSupported</a></li>
</ul></li>
</ul>



<h1><a id="user-content-oovooclient" class="anchor" href="#oovooclient" aria-hidden="true"><span class="octicon octicon-link"></span></a>ooVooClient</h1>

<h2><a id="user-content-constructor" class="anchor" href="#constructor" aria-hidden="true"><span class="octicon octicon-link"></span></a>Constructor</h2>

<p>Constructor ooVooClient which implements two modules the account and the avchat.</p>

<p><strong>Gets a parameters list:</strong> without parameters.</p>

<p><strong>Return a value:</strong> no result.</p>

<h2><a id="user-content-sharedinstance" class="anchor" href="#sharedinstance" aria-hidden="true"><span class="octicon octicon-link"></span></a>sharedInstance</h2>

<p>Get singleton reference to ooVooClient SDK. Note: You need set Context before using this method else exception will throws.</p>

<p><strong>Gets a parameters list:</strong> without parameters.</p>

<p><strong>Return a value</strong>:</p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td><strong>ooVooClient</strong></td>
<td>NA</td>
<td>Singleton reference to ooVooClient SDK</td>
</tr>
</tbody></table>

<h2><a id="user-content-getaccount" class="anchor" href="#getaccount" aria-hidden="true"><span class="octicon octicon-link"></span></a>getAccount</h2>

<p>Get ooVoo client account property. Use account object to perform operations such as: create account, login account, get profile ...</p>

<p><strong>Gets a parameters list:</strong> without parameters.</p>

<p><strong>Return a value:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td><strong>IAccount</strong></td>
<td>NA</td>
<td>Returns interface to ooVoo client Account service</td>
</tr>
</tbody></table>

<h2><a id="user-content-getavchat" class="anchor" href="#getavchat" aria-hidden="true"><span class="octicon octicon-link"></span></a>getAVChat</h2>

<p>Get ooVoo client audio video property. Use AVChat object to perform operation such as: get getVideoController, getAudioController, setListener, send....</p>

<p><strong>Parameters:</strong> without parameters.</p>

<p><strong>Return a value:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td><strong>AVChat</strong></td>
<td>NA</td>
<td>Returns interface to ooVoo client AVChat service</td>
</tr>
</tbody></table>

<h2><a id="user-content-isauthorized" class="anchor" href="#isauthorized" aria-hidden="true"><span class="octicon octicon-link"></span></a>isAuthorized</h2>

<p>The method allows define if was performed authorizing.</p>

<p><strong>Parameters:</strong> without parameters.</p>

<p><strong>Return a value:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td><strong>boolean</strong></td>
<td>NA</td>
<td>Returns true if was performed authorizing.</td>
</tr>
</tbody></table>

<h2><a id="user-content-isdevicesupported" class="anchor" href="#isdevicesupported" aria-hidden="true"><span class="octicon octicon-link"></span></a>isDeviceSupported</h2>

<p>The method allows to define if ooVoo SDK support this device.</p>

<p><strong>Parameters:</strong> without parameters.</p>

<p><strong>Return a value:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td><strong>boolean</strong></td>
<td>NA</td>
<td>Returns true if supported.</td>
</tr>
</tbody></table>

<h2><a id="user-content-setcontext" class="anchor" href="#setcontext" aria-hidden="true"><span class="octicon octicon-link"></span></a>setContext</h2>

<p>The static method allows to set application context.</p>

<p><strong>Gets a parameters list:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td><strong>Context</strong></td>
<td>ctx</td>
<td>Set application context.</td>
</tr>
</tbody></table>

<p><strong>Return a value:</strong> no result.</p>

<h2><a id="user-content-istablet" class="anchor" href="#istablet" aria-hidden="true"><span class="octicon octicon-link"></span></a>isTablet</h2>

<p>The static method allows to detect if this a device is tablet.</p>

<p><strong>Gets a parameters list:</strong> without parameters.</p>

<p><strong>Return a value:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td><strong>boolean</strong></td>
<td>----</td>
<td>Returns boolean value, if this a device is tablet.</td>
</tr>
</tbody></table>

<h2><a id="user-content-setsslpeerverify" class="anchor" href="#setsslpeerverify" aria-hidden="true"><span class="octicon octicon-link"></span></a>setSslPeerVerify</h2>

<p>The native method allows to set checking for of a secure connection.
An SSL certificate - a unique digital signature necessary for the organization of a secure connection between the client and the server.</p>

<p><strong>Gets a parameters list:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td><strong>boolean</strong></td>
<td>state</td>
<td>Define a secure connection.</td>
</tr>
</tbody></table>

<p><strong>Return a value:</strong> no result.</p>

<h2><a id="user-content-issslpeerverify" class="anchor" href="#issslpeerverify" aria-hidden="true"><span class="octicon octicon-link"></span></a>isSslPeerVerify</h2>

<p>The native method allows to detect if this a connection used a SSL verification.</p>

<p><strong>Gets a parameters list:</strong> without parameters.</p>

<p><strong>Return a value:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td><strong>boolean</strong></td>
<td>----</td>
<td>Returns Boolean value, if this a connection is a secure.</td>
</tr>
</tbody></table>

<h2><a id="user-content-authorizeclient" class="anchor" href="#authorizeclient" aria-hidden="true"><span class="octicon octicon-link"></span></a>authorizeClient</h2>

<p>The method allows to authorize access to ooVooClient SDK. This is async method, event will raised on main thread.</p>

<p><strong>Gets a parameters list:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td><strong>String</strong></td>
<td>app_token</td>
<td>The application token got after registration on site.</td>
</tr>
<tr>
<td><strong>String</strong></td>
<td>version</td>
<td>SDK user version.</td>
</tr>
<tr>
<td><strong>ooVooSdkResultListener</strong></td>
<td>result_receiver</td>
<td>The async listener which allows to get result on request.</td>
</tr>
</tbody></table>

<p><strong>Return a value:</strong> no result.</p>

<h2><a id="user-content-setlogger" class="anchor" href="#setlogger" aria-hidden="true"><span class="octicon octicon-link"></span></a>setLogger</h2>

<p>Associates a logging object with the SDK.</p>

<p><strong>Gets a parameters list:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td><strong>LoggerListener</strong></td>
<td>listener</td>
<td>The async listener which allows to get result on request.</td>
</tr>
<tr>
<td><strong>LogLevel</strong></td>
<td>level</td>
<td>The level of log.</td>
</tr>
</tbody></table>

<p><strong>Return a value:</strong> no result.</p>

<h2><a id="user-content-setloglevel" class="anchor" href="#setloglevel" aria-hidden="true"><span class="octicon octicon-link"></span></a>setLogLevel</h2>

<p>The static method allows to set a log level in the SDK.</p>

<p><strong>Gets a parameters list:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td><strong>LogLevel</strong></td>
<td>level</td>
<td>The level of log.</td>
</tr>
</tbody></table>

<p><strong>Return a value:</strong> no result.</p>

<h2><a id="user-content-getsdkversion" class="anchor" href="#getsdkversion" aria-hidden="true"><span class="octicon octicon-link"></span></a>getSdkVersion</h2>

<p>The method allows to get SDK version.</p>

<p><strong>Parameters:</strong> without parameters.</p>

<p><strong>Return a value:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td><strong>String</strong></td>
<td>----</td>
<td>Returns version of SDK.</td>
</tr>
</tbody></table>

<h2><a id="user-content-updateconfig" class="anchor" href="#updateconfig" aria-hidden="true"><span class="octicon octicon-link"></span></a>updateConfig</h2>

<p>The method allows to update user configuration and will sync local configuration for a user and backend version. Result contain only status of the operation.</p>

<p><strong>Gets a parameters list:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td><strong>ooVooSdkResultListener</strong></td>
<td>listener</td>
<td>The ASYNC listener which allows to get result on request.</td>
</tr>
</tbody></table>

<p><strong>Return a value:</strong> no result.</p>

<h1><a id="user-content-glperformanceutlis" class="anchor" href="#glperformanceutlis" aria-hidden="true"><span class="octicon octicon-link"></span></a>GLPerformanceUtlis</h1>

<h2><a id="user-content-getcurrentcpufrequency" class="anchor" href="#getcurrentcpufrequency" aria-hidden="true"><span class="octicon octicon-link"></span></a>getCurrentCpuFrequency</h2>

<p>The method allows to get the current frequency of CPU in Hz.</p>

<p><strong>Gets a parameters list:</strong> without parameters.</p>

<p><strong>Return a value:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td><strong>int</strong></td>
<td>----</td>
<td>Returns frequency in Hz.</td>
</tr>
</tbody></table>

<h2><a id="user-content-getenablethreshold" class="anchor" href="#getenablethreshold" aria-hidden="true"><span class="octicon octicon-link"></span></a>getEnableThreshold</h2>

<p>The method allows to get the maximum time for perform action with the current resolution. If the return value from getPerfValue is bigger than the value from getEnableThreshold, GPU buffer reading for that resolution is not suggested to be used in the app.</p>

<p><strong>Gets a parameters list:</strong> without parameters.</p>

<p><strong>Return a value:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td><strong>long</strong></td>
<td>----</td>
<td>Returns suggested value about the acceptable threshold in microseconds.</td>
</tr>
</tbody></table>

<h2><a id="user-content-getnumcore" class="anchor" href="#getnumcore" aria-hidden="true"><span class="octicon octicon-link"></span></a>getNumCore</h2>

<p>The method allows to get the number of the CPU core.</p>

<p><strong>Gets a parameters list:</strong> without parameters.</p>

<p><strong>Return a value:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td><strong>int</strong></td>
<td>----</td>
<td>Returns the number of cores.</td>
</tr>
</tbody></table>

<h2><a id="user-content-getperfvalue" class="anchor" href="#getperfvalue" aria-hidden="true"><span class="octicon octicon-link"></span></a>getPerfValue</h2>

<p>The method allows to get the test result for specific resolution. CIF would only be tested if the VGA cannot meet the "suggested enable threshold" If the resolution was not been test function will return -1.</p>

<p><strong>Gets a parameters list:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td><strong>String</strong></td>
<td>resolution</td>
<td>Available resolution VGA_PERFORMANCE / CIF_PERFORMANCE</td>
</tr>
</tbody></table>

<p><strong>Return a value:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td><strong>long</strong></td>
<td>----</td>
<td>Returns average time in microsecond of GPU buffer reading.</td>
</tr>
</tbody></table>

<h2><a id="user-content-istegradetected" class="anchor" href="#istegradetected" aria-hidden="true"><span class="octicon octicon-link"></span></a>isTegraDetected</h2>

<p>The method allows to get the number of the CPU core.</p>

<p><strong>Gets a parameters list:</strong> without parameters.</p>

<p><strong>Return a value:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td><strong>boolean</strong></td>
<td>----</td>
<td>Returns boolean value if this is Tegra.</td>
</tr>
</tbody></table>

<h1><a id="user-content-jniobject" class="anchor" href="#jniobject" aria-hidden="true"><span class="octicon octicon-link"></span></a>JNIObject</h1>

<h2><a id="user-content-isvalid" class="anchor" href="#isvalid" aria-hidden="true"><span class="octicon octicon-link"></span></a>isValid</h2>

<p>The method allows to check if the object is valid.</p>

<p><strong>Gets a parameters list:</strong> without parameters.</p>

<p><strong>Return a value:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td><strong>Boolean</strong></td>
<td>----</td>
<td>Returns Boolean value if is valid.</td>
</tr>
</tbody></table>

<h2><a id="user-content-release" class="anchor" href="#release" aria-hidden="true"><span class="octicon octicon-link"></span></a>release</h2>

<p>The method allows to release JNI object.</p>

<p><strong>Gets a parameters list:</strong> without parameters.</p>

<p><strong>Return a value:</strong> no result.</p>

<h1><a id="user-content-account" class="anchor" href="#account" aria-hidden="true"><span class="octicon octicon-link"></span></a>Account</h1>

<h2><a id="user-content-login" class="anchor" href="#login" aria-hidden="true"><span class="octicon octicon-link"></span></a>login</h2>

<p>The method allows you to login with an existing user.</p>

<p><strong>Gets a parameters list:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td><strong>String</strong></td>
<td>uid</td>
<td>The ID an existing user in ooVoo.</td>
</tr>
<tr>
<td><strong>ooVooSdkResultListener</strong></td>
<td>listener</td>
<td>The async listener which allows to get result on request.</td>
</tr>
</tbody></table>

<p><strong>Return a value:</strong> no result.</p>

<h2><a id="user-content-getid" class="anchor" href="#getid" aria-hidden="true"><span class="octicon octicon-link"></span></a>getID</h2>

<p>The method allows to get logged in account id.</p>

<p><strong>Gets a parameters list:</strong> without parameters.</p>

<p><strong>Return a value:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td><strong>String</strong></td>
<td>----</td>
<td>Returns an user ID.</td>
</tr>
</tbody></table>

<h2><a id="user-content-logout" class="anchor" href="#logout" aria-hidden="true"><span class="octicon octicon-link"></span></a>logout</h2>

<p>The method allows to perform logout an existing user.</p>

<p><strong>Gets a parameters list:</strong> without parameters.</p>

<p><strong>Return a value:</strong> no result.</p>

<h1><a id="user-content-device" class="anchor" href="#device" aria-hidden="true"><span class="octicon octicon-link"></span></a>Device </h1>

<h2><a id="user-content-getid-1" class="anchor" href="#getid-1" aria-hidden="true"><span class="octicon octicon-link"></span></a>getID</h2>

<p>The method allows to get ID of device.</p>

<p><strong>Gets a parameters list:</strong> without parameters.</p>

<p><strong>Return a value:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td><strong>String</strong></td>
<td>----</td>
<td>Returns a device ID.</td>
</tr>
</tbody></table>

<h2><a id="user-content-getname" class="anchor" href="#getname" aria-hidden="true"><span class="octicon octicon-link"></span></a>getName</h2>

<p>The method allows to get name of device.</p>

<p><strong>Gets a parameters list:</strong> without parameters.</p>

<p><strong>Return a value:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td><strong>String</strong></td>
<td>----</td>
<td>Returns a name ID.</td>
</tr>
</tbody></table>

<h1><a id="user-content-effect" class="anchor" href="#effect" aria-hidden="true"><span class="octicon octicon-link"></span></a>Effect</h1>

<h2><a id="user-content-getcategory" class="anchor" href="#getcategory" aria-hidden="true"><span class="octicon octicon-link"></span></a>getCategory</h2>

<p>The method allows to get category of the effect.</p>

<p><strong>Gets a parameters list:</strong> without parameters.</p>

<p><strong>Return a value:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td><strong>String</strong></td>
<td>----</td>
<td>Returns a category of the effect.</td>
</tr>
</tbody></table>

<h2><a id="user-content-geticonurl" class="anchor" href="#geticonurl" aria-hidden="true"><span class="octicon octicon-link"></span></a>getIconUrl</h2>

<p>The method allows to get URL to icon for the effect.</p>

<p><strong>Gets a parameters list:</strong> without parameters.</p>

<p><strong>Return a value:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td><strong>String</strong></td>
<td>----</td>
<td>Returns URL to icon for the effect.</td>
</tr>
</tbody></table>

<h2><a id="user-content-getid-2" class="anchor" href="#getid-2" aria-hidden="true"><span class="octicon octicon-link"></span></a>getID</h2>

<p>The method allows to get unique ID of the effect.</p>

<p><strong>Gets a parameters list:</strong> without parameters.</p>

<p><strong>Return a value:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td><strong>String</strong></td>
<td>----</td>
<td>Returns ID of the effect.</td>
</tr>
</tbody></table>

<h2><a id="user-content-getname-1" class="anchor" href="#getname-1" aria-hidden="true"><span class="octicon octicon-link"></span></a>getName</h2>

<p>The method allows to get name of the effect.</p>

<p><strong>Gets a parameters list:</strong> without parameters.</p>

<p><strong>Return a value:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td><strong>String</strong></td>
<td>----</td>
<td>Returns name of the effect.</td>
</tr>
</tbody></table>

<h2><a id="user-content-getpurchaseid" class="anchor" href="#getpurchaseid" aria-hidden="true"><span class="octicon octicon-link"></span></a>getPurchaseId</h2>

<p>The method allows to get unique static ID of the effect.</p>

<p><strong>Gets a parameters list:</strong> without parameters.</p>

<p><strong>Return a value:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td><strong>String</strong></td>
<td>----</td>
<td>Returns static ID of the effect.</td>
</tr>
</tbody></table>

<h1><a id="user-content-pluginfactory" class="anchor" href="#pluginfactory" aria-hidden="true"><span class="octicon octicon-link"></span></a>PluginFactory</h1>

<h2><a id="user-content-createplugininstance" class="anchor" href="#createplugininstance" aria-hidden="true"><span class="octicon octicon-link"></span></a>createPluginInstance</h2>

<p>The method allows to create a custom plugin and integrate him in ooVoo SDK.</p>

<p><strong>Gets a parameters list:</strong> without parameters.</p>

<p><strong>Return a value:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td><strong>long</strong></td>
<td>----</td>
<td>Returns unique ID of instance.</td>
</tr>
</tbody></table>

<h1><a id="user-content-oovoosdkresultlistener" class="anchor" href="#oovoosdkresultlistener" aria-hidden="true"><span class="octicon octicon-link"></span></a>ooVooSdkResultListener</h1>

<h2><a id="user-content-onresult" class="anchor" href="#onresult" aria-hidden="true"><span class="octicon octicon-link"></span></a>onResult</h2>

<p>The method allows to get all events from lower level of SDK.</p>

<p><strong>Gets a parameters list:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td><strong>ooVooSdkResult</strong></td>
<td>result</td>
<td>The async listener which allows to get result on requests.</td>
</tr>
</tbody></table>

<p><strong>Return a value: no result.</strong></p>

<h1><a id="user-content-oovoosdkresult" class="anchor" href="#oovoosdkresult" aria-hidden="true"><span class="octicon octicon-link"></span></a>ooVooSdkResult</h1>

<h2><a id="user-content-getresult" class="anchor" href="#getresult" aria-hidden="true"><span class="octicon octicon-link"></span></a>getResult</h2>

<p>The method allows to get a result on a request.</p>

<p><strong>Gets a parameters list:</strong> without parameters. <strong>Return a value:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td>*<em>sdk_error    *</em></td>
<td>----</td>
<td>Returns the result on a request.</td>
</tr>
</tbody></table>

<h2><a id="user-content-getdescription" class="anchor" href="#getdescription" aria-hidden="true"><span class="octicon octicon-link"></span></a>getDescription</h2>

<p>The method allows to get a description on a request.</p>

<p><strong>Gets a parameters list:</strong> without parameters.</p>

<p><strong>Return a value:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td>*<em>String    *</em></td>
<td>----</td>
<td>Returns the description on a request.</td>
</tr>
</tbody></table>

<h2><a id="user-content-getuserinfo" class="anchor" href="#getuserinfo" aria-hidden="true"><span class="octicon octicon-link"></span></a>getUserInfo</h2>

<p>The method allows to get additional information on a request.</p>

<p><strong>Gets a parameters list:</strong> without parameters.</p>

<p><strong>Return a value:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td><strong><code>Hashtable&lt;String, Object&gt;</code></strong></td>
<td>----</td>
<td>Returns the additional information on a request.</td>
</tr>
</tbody></table>

<h1><a id="user-content-loggerlistener" class="anchor" href="#loggerlistener" aria-hidden="true"><span class="octicon octicon-link"></span></a>LoggerListener</h1>

<h2><a id="user-content-loglevel" class="anchor" href="#loglevel" aria-hidden="true"><span class="octicon octicon-link"></span></a>LogLevel</h2>

<p>The enum allows to get the different levels of log.</p>

<p><strong>Parameters list:</strong></p>

<table><thead>
<tr>
<th>Values</th>
</tr>
</thead><tbody>
<tr>
<td><code>int</code></td>
</tr>
<tr>
<td>0</td>
</tr>
<tr>
<td>1</td>
</tr>
<tr>
<td>2</td>
</tr>
<tr>
<td>3</td>
</tr>
<tr>
<td>4</td>
</tr>
<tr>
<td>5</td>
</tr>
<tr>
<td>6</td>
</tr>
</tbody></table>

<h2><a id="user-content-fromint" class="anchor" href="#fromint" aria-hidden="true"><span class="octicon octicon-link"></span></a>fromInt</h2>

<p>The method allows to convert a log level from integer to enum.</p>

<p><strong>Gets a parameters list:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td><strong>int</strong></td>
<td>e</td>
<td>This is a log level in format integer.</td>
</tr>
</tbody></table>

<p><strong>Return a value:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td><strong>LogLevel</strong></td>
<td>----</td>
<td>Returns a log level.</td>
</tr>
</tbody></table>

<h2><a id="user-content-leveltoint" class="anchor" href="#leveltoint" aria-hidden="true"><span class="octicon octicon-link"></span></a>levelToInt</h2>

<p>The method allows to convert a log level to integer from enum.</p>

<p><strong>Gets a parameters list:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td><strong>LogLevel</strong></td>
<td>level</td>
<td>This is a log level in format enum.</td>
</tr>
</tbody></table>

<p><strong>Return a value:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td><strong>int</strong></td>
<td>----</td>
<td>Returns a log level.</td>
</tr>
</tbody></table>

<h2><a id="user-content-fromstring" class="anchor" href="#fromstring" aria-hidden="true"><span class="octicon octicon-link"></span></a>fromString</h2>

<p>The method allows to convert a log level from string to enum.</p>

<p><strong>Gets a parameters list:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td><strong>String</strong></td>
<td>s</td>
<td>This is a log level in format string.</td>
</tr>
</tbody></table>

<p><strong>Return a value:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td>LogLevel</td>
<td>----</td>
<td>Returns a log level.</td>
</tr>
</tbody></table>

<h2><a id="user-content-onlog" class="anchor" href="#onlog" aria-hidden="true"><span class="octicon octicon-link"></span></a>OnLog</h2>

<p>The method allows to get all events from lower level of SDK. Note: must provide an implementation for this method.</p>

<p><strong>Gets a parameters list:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td><strong>LogLevel</strong></td>
<td>level</td>
<td>This is a log level in format enum.</td>
</tr>
<tr>
<td><strong>String</strong></td>
<td>tag</td>
<td>This is ID of message.</td>
</tr>
<tr>
<td><strong>String</strong></td>
<td>message</td>
<td>This is a body message.</td>
</tr>
</tbody></table>

<p><strong>Return a value:</strong> no result.</p>

<h1><a id="user-content-avchat" class="anchor" href="#avchat" aria-hidden="true"><span class="octicon octicon-link"></span></a>AVChat</h1>

<h2><a id="user-content-conferencestate" class="anchor" href="#conferencestate" aria-hidden="true"><span class="octicon octicon-link"></span></a>ConferenceState</h2>

<p>The enum allows to get the different the conference state.</p>

<p><strong>Parameters list:</strong> Joined, Disconnected</p>

<h2><a id="user-content-setlistener" class="anchor" href="#setlistener" aria-hidden="true"><span class="octicon octicon-link"></span></a>setListener</h2>

<p>The method allows to set handler for receiving conference event from SDK.</p>

<p><strong>Gets a parameters list:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td>AVChatListener</td>
<td>listener</td>
<td>The async listener which allows to set handler for receiving conference event.</td>
</tr>
</tbody></table>

<p><strong>Return a value:</strong> no result.</p>

<h2><a id="user-content-join" class="anchor" href="#join" aria-hidden="true"><span class="octicon octicon-link"></span></a>join</h2>

<p>The method allows to perform a join conference call.</p>

<p><strong>Gets a parameters list:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td>AVChatListener</td>
<td>listener</td>
<td>The async listener which allows to set handler for receiving conference event.</td>
</tr>
</tbody></table>

<p><strong>Return a value:</strong> no result.</p>

<h2><a id="user-content-leave" class="anchor" href="#leave" aria-hidden="true"><span class="octicon octicon-link"></span></a>leave</h2>

<p>The method allows to perform a leave from conference call.</p>

<p><strong>Gets a parameters list:</strong> without parameters.</p>

<p><strong>Return a value:</strong> no result.</p>

<h2><a id="user-content-senddata" class="anchor" href="#senddata" aria-hidden="true"><span class="octicon octicon-link"></span></a>sendData</h2>

<p>The method allows to send a message to the user specification.</p>

<p><strong>Gets a parameters list:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td>String</td>
<td>uid</td>
<td>Specifies the user, to which the message is sent.</td>
</tr>
<tr>
<td>byte[]</td>
<td>msg</td>
<td>The message for sending.</td>
</tr>
</tbody></table>

<p><strong>Return a value:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td>sdk_error</td>
<td>----</td>
<td>Returns a status about sending.</td>
</tr>
</tbody></table>

<h2><a id="user-content-senddata-1" class="anchor" href="#senddata-1" aria-hidden="true"><span class="octicon octicon-link"></span></a>sendData</h2>

<p>The method allows to send a message to all users in conference session.</p>

<p><strong>Gets a parameters list:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td>byte[]</td>
<td>msg</td>
<td>The message for sending.</td>
</tr>
</tbody></table>

<p><strong>Return a value:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td>sdk_error</td>
<td>----</td>
<td>Returns a status about sending.</td>
</tr>
</tbody></table>

<h2><a id="user-content-registerplugin" class="anchor" href="#registerplugin" aria-hidden="true"><span class="octicon octicon-link"></span></a>registerPlugin</h2>

<p>The method allows to register a custom plugin implementation for use in AVChat.</p>

<p><strong>Gets a parameters list:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td>PluginFactory</td>
<td>plugin</td>
<td>The interface allow transfer custom plugin implementation to our SDK</td>
</tr>
</tbody></table>

<p><strong>Return a value:</strong> no result.</p>

<h2><a id="user-content-unregisterplugin" class="anchor" href="#unregisterplugin" aria-hidden="true"><span class="octicon octicon-link"></span></a>unregisterPlugin</h2>

<p>The method allows to un-register a custom plugin for use in AVChat.</p>

<p><strong>Gets a parameters list:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td>PluginFactory</td>
<td>plugin</td>
<td>The interface allow to cancel custom plugin to our SDK</td>
</tr>
</tbody></table>

<p><strong>Return a value:</strong> no result.</p>

<h2><a id="user-content-isincallmessagespermit" class="anchor" href="#isincallmessagespermit" aria-hidden="true"><span class="octicon octicon-link"></span></a>isInCallMessagesPermit</h2>

<p>The method allows to check if you can send a message via conference.</p>

<p><strong>Gets a parameters list:</strong> without parameters.</p>

<p><strong>Return a value:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td>boolean</td>
<td>----</td>
<td>Returns boolean value, if you can send a message.</td>
</tr>
</tbody></table>

<h2><a id="user-content-getavailableresolutions" class="anchor" href="#getavailableresolutions" aria-hidden="true"><span class="octicon octicon-link"></span></a>getAvailableResolutions</h2>

<p>The method allows to get available a resolution list in current a call.</p>

<p><strong>Gets a parameters list:</strong> without parameters.</p>

<p><strong>Return a value:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td>ArrayList&lt;VideoController.ResolutionLevel&gt;</td>
<td>----</td>
<td>Returns a list resolutions.</td>
</tr>
</tbody></table>

<h2><a id="user-content-isresolutionsupported" class="anchor" href="#isresolutionsupported" aria-hidden="true"><span class="octicon octicon-link"></span></a>isResolutionSupported</h2>

<p>The method allows to check, if this a resolution is supported.</p>

<p><strong>Gets a parameters list:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td>VideoController.ResolutionLevel</td>
<td>level</td>
<td>This is a resolution for checking.</td>
</tr>
</tbody></table>

<p><strong>Return a value:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td>boolean</td>
<td>----</td>
<td>Returns boolean value, If there is support for the requested resolution.</td>
</tr>
</tbody></table>

<h2><a id="user-content-getvideocontroller" class="anchor" href="#getvideocontroller" aria-hidden="true"><span class="octicon octicon-link"></span></a>getVideoController</h2>

<p>The method allows to get to video controller interface.</p>

<p><strong>Gets a parameters list:</strong> without parameters.</p>

<p><strong>Return a value:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td>VideoController</td>
<td>----</td>
<td>Returns the interface of a video controller.</td>
</tr>
</tbody></table>

<h2><a id="user-content-getaudiocontroller" class="anchor" href="#getaudiocontroller" aria-hidden="true"><span class="octicon octicon-link"></span></a>getAudioController</h2>

<p>The method allows to get to audio controller interface.</p>

<p><strong>Gets a parameters list:</strong> without parameters.</p>

<p><strong>Return a value:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td>AudioController</td>
<td>----</td>
<td>Returns the interface of an audio controller.</td>
</tr>
</tbody></table>

<p> </p>

<h2><a id="user-content-avchatlistener" class="anchor" href="#avchatlistener" aria-hidden="true"><span class="octicon octicon-link"></span></a>AVChatListener</h2>

<h3><a id="user-content-onparticipantjoined" class="anchor" href="#onparticipantjoined" aria-hidden="true"><span class="octicon octicon-link"></span></a>onParticipantJoined</h3>

<p>The method allows to receive an event listener that a participant joined to av chat session.</p>

<p><strong>Gets a parameters list:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td>Participant</td>
<td>participant</td>
<td>This is participant ID.</td>
</tr>
<tr>
<td>String</td>
<td>userData</td>
<td>This is user's additional information but data can be null.</td>
</tr>
</tbody></table>

<p><strong>Return a value</strong>: no result.</p>

<h3><a id="user-content-onparticipantleft" class="anchor" href="#onparticipantleft" aria-hidden="true"><span class="octicon octicon-link"></span></a>onParticipantLeft</h3>

<p>The method allows to receive an event listener that a participant left the session.</p>

<p><strong>Gets a parameters list:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td>Participant</td>
<td>participant</td>
<td>This is participant ID.</td>
</tr>
</tbody></table>

<p><strong>Return a value:</strong> no result.  </p>

<h3><a id="user-content-onconferencestatechanged" class="anchor" href="#onconferencestatechanged" aria-hidden="true"><span class="octicon octicon-link"></span></a>onConferenceStateChanged</h3>

<p>The method allows to receive an event listener about changing in session.</p>

<p><strong>Gets a parameters list:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td>ConferenceState</td>
<td>state</td>
<td>This is enum conference state.</td>
</tr>
<tr>
<td>sdk_error</td>
<td>errorCode</td>
<td>This is an error code about changing a state of conference.</td>
</tr>
</tbody></table>

<p><strong>Return a value:</strong> no result.</p>

<h3><a id="user-content-onreceivedata" class="anchor" href="#onreceivedata" aria-hidden="true"><span class="octicon octicon-link"></span></a>onReceiveData</h3>

<p>The method allows to receive any data that had been sent to the user. <strong>Gets a parameters list:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td><strong>String</strong></td>
<td>uid</td>
<td>This is user ID.</td>
</tr>
<tr>
<td><strong>byte[]</strong></td>
<td>buffer</td>
<td>This is any data.</td>
</tr>
</tbody></table>

<p><strong>Return a value:</strong> no result.</p>

<h3><a id="user-content-onconferenceerror" class="anchor" href="#onconferenceerror" aria-hidden="true"><span class="octicon octicon-link"></span></a>onConferenceError</h3>

<p>The method allows to receive an event listener about error in conference session.</p>

<p><strong>Gets a parameters list:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td>sdk_error</td>
<td>errorCode</td>
<td>This is an error code about a conference.</td>
</tr>
</tbody></table>

<p><strong>Return a value:</strong> no result.  </p>

<h3><a id="user-content-onnetworkreliability" class="anchor" href="#onnetworkreliability" aria-hidden="true"><span class="octicon octicon-link"></span></a>onNetworkReliability</h3>

<p>The method allows to receive an information about network state.</p>

<p><strong>Gets a parameters list:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td>int</td>
<td>score</td>
<td>This is a network state.</td>
</tr>
</tbody></table>

<p><strong>Return a value:</strong> no result.  </p>

<h1><a id="user-content-participant" class="anchor" href="#participant" aria-hidden="true"><span class="octicon octicon-link"></span></a>Participant</h1>

<h2><a id="user-content-participanttype" class="anchor" href="#participanttype" aria-hidden="true"><span class="octicon octicon-link"></span></a>ParticipantType</h2>

<p>The enum allows to get a different a types of participant.</p>

<p><strong>Parameters list:</strong> VoIP</p>

<h2><a id="user-content-getid-3" class="anchor" href="#getid-3" aria-hidden="true"><span class="octicon octicon-link"></span></a>getID</h2>

<p>The method allows to get participant ID in conference.</p>

<p><strong>Gets a parameters list:</strong> without parameters.</p>

<p><strong>Return a value:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td>String</td>
<td>----</td>
<td>Returns the participant ID.</td>
</tr>
</tbody></table>

<h2><a id="user-content-gettype" class="anchor" href="#gettype" aria-hidden="true"><span class="octicon octicon-link"></span></a>getType</h2>

<p>The method allows to get type connect of participant.</p>

<p><strong>Gets a parameters list:</strong> without parameters.</p>

<p><strong>Return a value:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td>ParticipantType</td>
<td>----</td>
<td>Returns type of connect.</td>
</tr>
</tbody></table>

<p> </p>

<h1><a id="user-content-audiocontroller" class="anchor" href="#audiocontroller" aria-hidden="true"><span class="octicon octicon-link"></span></a>AudioController</h1>

<h2><a id="user-content-audioroutemode" class="anchor" href="#audioroutemode" aria-hidden="true"><span class="octicon octicon-link"></span></a>AudioRouteMode</h2>

<p>The enum allows to get the different an audio routes.</p>

<p><strong>Parameters list:</strong> AudioRouteModeVoiceChat, AudioRouteModeVideoChat</p>

<h2><a id="user-content-setlistener-1" class="anchor" href="#setlistener-1" aria-hidden="true"><span class="octicon octicon-link"></span></a>setListener</h2>

<p>The method allows to set handler for receiving conference event from audio controller.</p>

<p><strong>Gets a parameters list:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td>AudioControllerListener</td>
<td>listener</td>
<td>The async listener which allows to set handler for receiving conference event.</td>
</tr>
</tbody></table>

<p><strong>Return a value: no result.</strong></p>

<h2><a id="user-content-initaudio" class="anchor" href="#initaudio" aria-hidden="true"><span class="octicon octicon-link"></span></a>initAudio</h2>

<p>The method audio record/playback module. It's recommended to call this method before calling to join method.</p>

<p><strong>Gets a parameters list:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td>ooVooSdkResultListener</td>
<td>completion</td>
<td>The async listener which allows to get result on request.</td>
</tr>
</tbody></table>

<p><strong>Return a value:</strong> no result.</p>

<h2><a id="user-content-uninitaudio" class="anchor" href="#uninitaudio" aria-hidden="true"><span class="octicon octicon-link"></span></a>uninitAudio</h2>

<p>The method allows to perform un-init audio record/playback module.</p>

<p><strong>Gets a parameters list:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td>ooVooSdkResultListener</td>
<td>completion</td>
<td>The async listener which allows to get result on request.</td>
</tr>
</tbody></table>

<p><strong>Return a value:</strong> no result.</p>

<h2><a id="user-content-isplaybackmuted" class="anchor" href="#isplaybackmuted" aria-hidden="true"><span class="octicon octicon-link"></span></a>isPlaybackMuted</h2>

<p>The method allows to check if playback current state of audio stream mute or unmute.</p>

<p><strong>Gets a parameters list:</strong> without parameters. <strong>Return a value:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td>boolean</td>
<td>----</td>
<td>Returns boolean value about of the state an audio stream.</td>
</tr>
</tbody></table>

<h2><a id="user-content-isrecordmuted" class="anchor" href="#isrecordmuted" aria-hidden="true"><span class="octicon octicon-link"></span></a>isRecordMuted</h2>

<p>The method allows to check if record current state mute or unmute.</p>

<p>Gets a parameters list: without parameters.</p>

<p><strong>Return a value:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td>boolean</td>
<td>----</td>
<td>Returns boolean value about of the state a record.</td>
</tr>
</tbody></table>

<h2><a id="user-content-setrecordmuted" class="anchor" href="#setrecordmuted" aria-hidden="true"><span class="octicon octicon-link"></span></a>setRecordMuted</h2>

<p>The method allows to set record current state mute or unmute.</p>

<p><strong>Gets a parameters list:</strong> without parameters.</p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td>boolean</td>
<td>state</td>
<td>Defines boolean value about of the state a record.</td>
</tr>
</tbody></table>

<p><strong>Return a value:</strong> no result.</p>

<h2><a id="user-content-setplaybackmuted" class="anchor" href="#setplaybackmuted" aria-hidden="true"><span class="octicon octicon-link"></span></a>setPlaybackMuted</h2>

<p>The method allows to set playback current state of audio stream mute or unmute.</p>

<p><strong>Gets a parameters list:</strong> without parameters.</p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td>boolean</td>
<td>state</td>
<td>Defines boolean value about of the state an audio stream.</td>
</tr>
</tbody></table>

<p><strong>Return a value:</strong> no result.</p>

<h2><a id="user-content-getaudioroutecontroller" class="anchor" href="#getaudioroutecontroller" aria-hidden="true"><span class="octicon octicon-link"></span></a>getAudioRouteController</h2>

<p>The method allows to get audio route manager interface.</p>

<p><strong>Gets a parameters list:</strong> without parameters.</p>

<p><strong>Return a value:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td>AudioRouteController</td>
<td>----</td>
<td>Returns audio route manager.</td>
</tr>
</tbody></table>

<h2><a id="user-content-setaudioroutemode" class="anchor" href="#setaudioroutemode" aria-hidden="true"><span class="octicon octicon-link"></span></a>setAudioRouteMode</h2>

<p>The method allows to set audio route mode, exists two modes <em>AudioRouteModeVideoChat</em> and <em>AudioRouteModeVoiceChat</em>.</p>

<p><em>AudioRouteModeVoiceChat</em> - audio will start with audio directed to earpiece.</p>

<p><em>AudioRouteModeVideoChat</em> - audio will start with audio directed to speaker.</p>

<p><strong>Gets a parameters list:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td>AudioRouteMode</td>
<td>mode</td>
<td>This is mode for audio routes.</td>
</tr>
</tbody></table>

<p><strong>Return a value:</strong> no result.
 </p>

<h2><a id="user-content-audiocontrollerlistener" class="anchor" href="#audiocontrollerlistener" aria-hidden="true"><span class="octicon octicon-link"></span></a>AudioControllerListener</h2>

<h3><a id="user-content-onaudiotransmitstatechanged" class="anchor" href="#onaudiotransmitstatechanged" aria-hidden="true"><span class="octicon octicon-link"></span></a>onAudioTransmitStateChanged</h3>

<p>The method allows to receive an event listener, that an audio transmitter has been changed.</p>

<p><strong>Gets a parameters list:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td>boolean</td>
<td>state</td>
<td>This is a state show if audio transmit has been changed.</td>
</tr>
<tr>
<td>sdk_error</td>
<td>error</td>
<td>This is an error code about changing.</td>
</tr>
</tbody></table>

<p><strong>Return a value:</strong> no result.</p>

<h3><a id="user-content-onaudioreceivestatechanged" class="anchor" href="#onaudioreceivestatechanged" aria-hidden="true"><span class="octicon octicon-link"></span></a>onAudioReceiveStateChanged</h3>

<p>The method allows to receive an event listener, that audio receiver has been changed.</p>

<p><strong>Gets a parameters list:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td>boolean</td>
<td>state</td>
<td>This is a state show if audio transmit has been changed.</td>
</tr>
<tr>
<td>sdk_error</td>
<td>error</td>
<td>This is an error code about changing.</td>
</tr>
</tbody></table>

<p><strong>Return a value: no result.</strong></p>

<h3><a id="user-content-onmicrophonestatechange" class="anchor" href="#onmicrophonestatechange" aria-hidden="true"><span class="octicon octicon-link"></span></a>onMicrophoneStateChange</h3>

<p>The method allows to receive an event listener, that microphone status has been changed.</p>

<p><strong>Gets a parameters list:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td>boolean</td>
<td>on</td>
<td>This is a status of microphone has been changed.</td>
</tr>
<tr>
<td>sdk_error</td>
<td>error</td>
<td>This is an error code about changing.</td>
</tr>
</tbody></table>

<p><strong>Return a value:</strong> no result.</p>

<h3><a id="user-content-onspeakerstatechange" class="anchor" href="#onspeakerstatechange" aria-hidden="true"><span class="octicon octicon-link"></span></a>onSpeakerStateChange</h3>

<p>The method allows to receive an event listener, that speaker status has been changed.</p>

<p><strong>Gets a parameters list:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td>boolean</td>
<td>on</td>
<td>This is a status of speaker has been changed.</td>
</tr>
<tr>
<td>sdk_error</td>
<td>error</td>
<td>This is an error code about changing.</td>
</tr>
</tbody></table>

<p><strong>Return a value:</strong> no result.  </p>

<h1><a id="user-content-audioroute" class="anchor" href="#audioroute" aria-hidden="true"><span class="octicon octicon-link"></span></a>AudioRoute</h1>

<h2><a id="user-content-getname-2" class="anchor" href="#getname-2" aria-hidden="true"><span class="octicon octicon-link"></span></a>getName</h2>

<p>The method allows to get name of audio route.</p>

<p><strong>Gets a parameters list:</strong> without parameters.</p>

<p><strong>Return a value:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td>String</td>
<td>----</td>
<td>Returns name of audio route .</td>
</tr>
</tbody></table>

<h2><a id="user-content-getrouteid" class="anchor" href="#getrouteid" aria-hidden="true"><span class="octicon octicon-link"></span></a>getRouteId</h2>

<p>The method allows to get ID of audio route.</p>

<p><strong>Gets a parameters list:</strong> without parameters.</p>

<p><strong>Return a value:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td>int</td>
<td>----</td>
<td>Returns ID of audio route .</td>
</tr>
</tbody></table>

<h2><a id="user-content-isactive" class="anchor" href="#isactive" aria-hidden="true"><span class="octicon octicon-link"></span></a>isActive</h2>

<p>The method allows to check if current route is active.</p>

<p><strong>Gets a parameters list:</strong> without parameters.</p>

<p><strong>Return a value:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td>int</td>
<td>----</td>
<td>Returns true if audio route is active.</td>
</tr>
</tbody></table>

<h1><a id="user-content-audioroutecontroller" class="anchor" href="#audioroutecontroller" aria-hidden="true"><span class="octicon octicon-link"></span></a>AudioRouteController</h1>

<h2><a id="user-content-getroutes" class="anchor" href="#getroutes" aria-hidden="true"><span class="octicon octicon-link"></span></a>getRoutes</h2>

<p>The method allows to get list available of audio routes.</p>

<p><strong>Gets a parameters list:</strong> without parameters.</p>

<p><strong>Return a value:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td>ArrayList</td>
<td>----</td>
<td>Returns list of audio routes.</td>
</tr>
</tbody></table>

<h2><a id="user-content-setlistener-2" class="anchor" href="#setlistener-2" aria-hidden="true"><span class="octicon octicon-link"></span></a>setListener</h2>

<p>The method allows to set handler for receiving the event from the audio route controller.</p>

<p><strong>Gets a parameters list:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td>AudioRouteControllerListener</td>
<td>listener</td>
<td>The async listener which allows to set handler for receiving the event.</td>
</tr>
</tbody></table>

<p><strong>Return a value:</strong> no result.</p>

<h2><a id="user-content-setroute" class="anchor" href="#setroute" aria-hidden="true"><span class="octicon octicon-link"></span></a>setRoute</h2>

<p>The method allows to select an audio route.</p>

<p><strong>Gets a parameters list:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td>AudioRoute</td>
<td>route</td>
<td>Audio route for setting.</td>
</tr>
</tbody></table>

<p><strong>Return a value:</strong>  no result.</p>

<h2><a id="user-content-audioroutecontrollerlistener" class="anchor" href="#audioroutecontrollerlistener" aria-hidden="true"><span class="octicon octicon-link"></span></a>AudioRouteControllerListener</h2>

<h3><a id="user-content-onaudioroutechanged" class="anchor" href="#onaudioroutechanged" aria-hidden="true"><span class="octicon octicon-link"></span></a>onAudioRouteChanged</h3>

<p>The method allows to receive an event listener, that an audio route has been changed.</p>

<p><strong>Gets a parameters list:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td>AudioRoute</td>
<td>old_route</td>
<td>This is show previous position of audio route.</td>
</tr>
<tr>
<td>AudioRoute</td>
<td>new_route</td>
<td>This is show current position of audio route.</td>
</tr>
</tbody></table>

<p><strong>Return a value:</strong> no result.</p>

<h1><a id="user-content-videocontroller" class="anchor" href="#videocontroller" aria-hidden="true"><span class="octicon octicon-link"></span></a>VideoController</h1>

<h2><a id="user-content-resolutionlevel" class="anchor" href="#resolutionlevel" aria-hidden="true"><span class="octicon octicon-link"></span></a>ResolutionLevel</h2>

<p>The enum allows to get the different resolution.</p>

<p><strong>Parameters list:</strong> ResolutionLevelNotSpecified, ResolutionLevelLow, ResolutionLevelMed, ResolutionLevelHigh, ResolutionLevelHD</p>

<h2><a id="user-content-videoconfigkey" class="anchor" href="#videoconfigkey" aria-hidden="true"><span class="octicon octicon-link"></span></a>VideoConfigKey</h2>

<p>The enum allows to get the key of video configuration.</p>

<p><strong>Parameters list:</strong> kVideoCfgCaptureDeviceId, kVideoCfgResolution, kVideoCfgFps, kVideoCfgEffectId</p>

<h2><a id="user-content-getconfig" class="anchor" href="#getconfig" aria-hidden="true"><span class="octicon octicon-link"></span></a>getConfig</h2>

<p>The method allows to get configuration according to with a key.</p>

<p><strong>Gets a parameters list:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td>VideoConfigKey</td>
<td>key</td>
<td>Key of the video configuration.</td>
</tr>
</tbody></table>

<p><strong>Return a value:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td>String</td>
<td>----</td>
<td>Returns configuration key.</td>
</tr>
</tbody></table>

<h2><a id="user-content-setconfig" class="anchor" href="#setconfig" aria-hidden="true"><span class="octicon octicon-link"></span></a>setConfig</h2>

<p>The method allows to set configuration according to with a key.</p>

<p><strong>Gets a parameters list:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td>VideoConfigKey</td>
<td>key</td>
<td>Key of the video configuration.</td>
</tr>
</tbody></table>

<p><strong>Return a value:</strong> no result.</p>

<h2><a id="user-content-setlistener-3" class="anchor" href="#setlistener-3" aria-hidden="true"><span class="octicon octicon-link"></span></a>setListener</h2>

<p>The method allows to set handler for receiving conference event from video controller.</p>

<p><strong>Gets a parameters list:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td>IVideoControllerListener</td>
<td>listener</td>
<td>The async listener which allows to set handler for receiving conference event.</td>
</tr>
</tbody></table>

<p><strong>Return a value:</strong> no result.</p>

<h2><a id="user-content-setactiveresolution" class="anchor" href="#setactiveresolution" aria-hidden="true"><span class="octicon octicon-link"></span></a>setActiveResolution</h2>

<p>The method allows to define the specific resolution for a camera.</p>

<p><strong>Gets a parameters list:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td>CameraResolutionLevel</td>
<td>level</td>
<td>Defines the resolution of camera.</td>
</tr>
</tbody></table>

<p><strong>Return a value:</strong> no result.</p>

<p> </p>

<h2><a id="user-content-getactiveresolution" class="anchor" href="#getactiveresolution" aria-hidden="true"><span class="octicon octicon-link"></span></a>getActiveResolution</h2>

<p>The method allows to get the resolution current the camera in uses.</p>

<p><strong>The method is depricated :</strong></p>

<p>Use instead</p>

<p>setConfig( VideoConfigKey.kVideoCfgResolution.ordinal(), ""+level.ordinal() );</p>

<p><strong>Gets a parameters list:</strong> without parameters. <strong>Return a value:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td>CameraResolutionLevel</td>
<td>----</td>
<td>Returns the resolution of current camera.</td>
</tr>
</tbody></table>

<h2><a id="user-content-setfps" class="anchor" href="#setfps" aria-hidden="true"><span class="octicon octicon-link"></span></a>setFps</h2>

<p>The method allows to define the frames per second for a video.</p>

<p><strong>The method is depricated :</strong></p>

<p>Use instead</p>

<p>setConfig( VideoConfigKey.kVideoCfgFps, "" + fps );.</p>

<p><strong>Gets a parameters list:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td>int</td>
<td>fps</td>
<td>Defines the frames per second for a video.</td>
</tr>
</tbody></table>

<p><strong>Return a value:</strong> no result.</p>

<h2><a id="user-content-getfps" class="anchor" href="#getfps" aria-hidden="true"><span class="octicon octicon-link"></span></a>getFps</h2>

<p>The method allows to get the frames per second for a video.</p>

<p><strong>The method is depricated :</strong></p>

<p>Use instead</p>

<p>String fps_value = getConfig( VideoConfigKey.kVideoCfgFps);</p>

<p>int fps    =   Integer.parseInt( fps_value.trim() );</p>

<p><strong>Gets a parameters list:</strong> without parameters.</p>

<p><strong>Return a value:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td>int</td>
<td>----</td>
<td>Returns the frames per second for a video.</td>
</tr>
</tbody></table>

<p> </p>

<h2><a id="user-content-setactiveeffect" class="anchor" href="#setactiveeffect" aria-hidden="true"><span class="octicon octicon-link"></span></a>setActiveEffect</h2>

<p>The method allows to define the effect for a video.</p>

<p><strong>The method is depricated :</strong></p>

<p>Use instead</p>

<p>setConfig( VideoConfigKey.kVideoCfgEffectId, effect.getID() );</p>

<p><strong>Gets a parameters list:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td>IEffect</td>
<td>effect</td>
<td>Defines the effect for a video.</td>
</tr>
</tbody></table>

<p><strong>Return a value:</strong> no result.</p>

<h2><a id="user-content-getactiveeffect" class="anchor" href="#getactiveeffect" aria-hidden="true"><span class="octicon octicon-link"></span></a>getActiveEffect</h2>

<p>The method allows to get the effect for a video.</p>

<p><strong>The method is depricated :</strong></p>

<p>Use instead</p>

<pre><code> String effect_id = getConfig( VideoConfigKey.kVideoCfgEffectId);

if( effect_id != null ) {

        ArrayList&lt;Effect&gt; effects = getEffectList();

        LogSdk.d( TAG, "Application -&gt; effects " + effects );

        if( effects != null ) {

            for( Effect effect : effects )

                {
                    if( effect.getID().equalsIgnoreCase( effect_id )) {

                        return effect;

                    }

                }

        }

    }
</code></pre>

<p><strong>Gets a parameters list:</strong> without parameters.</p>

<p><strong>Return a value:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td>IEffect</td>
<td>----</td>
<td>Returns the effect for a video.</td>
</tr>
</tbody></table>

<h2><a id="user-content-setactivedevice" class="anchor" href="#setactivedevice" aria-hidden="true"><span class="octicon octicon-link"></span></a>setActiveDevice</h2>

<p>The method allows to define type of camera for current use, a front camera or a back camera.</p>

<p><strong>The method is depricated :</strong></p>

<p>Use instead</p>

<p>setConfig( VideoConfigKey.kVideoCfgCaptureDeviceId, device.getID() );</p>

<p><strong>Gets a parameters list:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td>IDevice    device    Defines type of camera for use.</td>
<td></td>
<td></td>
</tr>
</tbody></table>

<p><strong>Return a value:</strong> no result.</p>

<p> </p>

<h2><a id="user-content-getactivedevice" class="anchor" href="#getactivedevice" aria-hidden="true"><span class="octicon octicon-link"></span></a>getActiveDevice</h2>

<p>The method allows to get the type of camera used at the moment.</p>

<p><strong>The method is depricated :</strong></p>

<p>Use instead</p>

<pre><code>String device_id = getConfig( VideoConfigKey.kVideoCfgCaptureDeviceId );

    if( device_id != null ) {

        ArrayList&lt;VideoDevice&gt; devices = getDeviceList();

        if( devices != null ) {

            for( VideoDevice device : devices ) {

                if( device.getID().equalsIgnoreCase( device_id )) {

                    return device;

                }

            }

        }

    }
</code></pre>

<p><strong>Gets a parameters list:</strong> without parameters.</p>

<p><strong>Return a value:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td>IDevice</td>
<td>----</td>
<td>Returns the camera used on the moment.</td>
</tr>
</tbody></table>

<h2><a id="user-content-openpreview" class="anchor" href="#openpreview" aria-hidden="true"><span class="octicon octicon-link"></span></a>openPreview</h2>

<p>The method allows to start get the video captures from camera. Camera must be opened before opening preview.</p>

<p><strong>Gets a parameters list:</strong> without parameters.</p>

<p><strong>Return a value:</strong> no result.</p>

<h2><a id="user-content-closepreview" class="anchor" href="#closepreview" aria-hidden="true"><span class="octicon octicon-link"></span></a>closePreview</h2>

<p>The method allows to stop get the video captures from camera.</p>

<p><strong>Gets a parameters list:</strong> without parameters.</p>

<p><strong>Return a value:</strong> no result.</p>

<h2><a id="user-content-opencamera" class="anchor" href="#opencamera" aria-hidden="true"><span class="octicon octicon-link"></span></a>openCamera</h2>

<p>The method allows to initialize the camera for use.</p>

<p><strong>Gets a parameters list:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td>Activity</td>
<td>parent</td>
<td>Defines the activity with which will be to interact a camera.</td>
</tr>
</tbody></table>

<p><strong>Return a value:</strong> no result.</p>

<h2><a id="user-content-closecamera" class="anchor" href="#closecamera" aria-hidden="true"><span class="octicon octicon-link"></span></a>closeCamera</h2>

<p>The method allows finalize to use the camera.</p>

<p><strong>Return a value:</strong> no result.</p>

<h2><a id="user-content-starttransmit" class="anchor" href="#starttransmit" aria-hidden="true"><span class="octicon octicon-link"></span></a>startTransmit</h2>

<p>The method allows to start transmit video.</p>

<p><strong>Return a value:</strong> no result.</p>

<h2><a id="user-content-stoptransmit" class="anchor" href="#stoptransmit" aria-hidden="true"><span class="octicon octicon-link"></span></a>stopTransmit</h2>

<p>The method allows to stop transmit video.</p>

<p><strong>Return a value:</strong> no result.</p>

<h2><a id="user-content-istransmited" class="anchor" href="#istransmited" aria-hidden="true"><span class="octicon octicon-link"></span></a>isTransmited</h2>

<p>The method allows to check if the video is transmitted at the moment.</p>

<p><strong>Gets a parameters list:</strong> without parameters.</p>

<p><strong>Return a value:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td>boolean</td>
<td>----</td>
<td>Returns the boolean value about transmission a video.</td>
</tr>
</tbody></table>

<h2><a id="user-content-bindrender" class="anchor" href="#bindrender" aria-hidden="true"><span class="octicon octicon-link"></span></a>bindRender</h2>

<p>The method allows to add the specified video stream at a particular VideoView from a   particular user in conference.</p>

<p><strong>Gets a parameters list:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td><strong>String</strong></td>
<td>uid</td>
<td>Specifies the user ID to which belongs to the video stream.</td>
</tr>
<tr>
<td><strong>VideoRender</strong></td>
<td>render</td>
<td>Defines the VideoView in which will be show video stream.</td>
</tr>
</tbody></table>

<p><strong>Return a value:</strong> no result.</p>

<h2><a id="user-content-unbindrender" class="anchor" href="#unbindrender" aria-hidden="true"><span class="octicon octicon-link"></span></a>unbindRender</h2>

<p>The method allows to remove the specific video stream at a particular VideoView from a particular user in conference.</p>

<p><strong>Gets a parameters list:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td><strong>String</strong></td>
<td>uid</td>
<td>Specifies the user ID to which belongs to the video stream.</td>
</tr>
<tr>
<td><strong>VideoRender</strong></td>
<td>render</td>
<td>Defines the VideoView in which will be removed video stream.</td>
</tr>
</tbody></table>

<p><strong>Return a value:</strong> no result.</p>

<h2><a id="user-content-registerremote" class="anchor" href="#registerremote" aria-hidden="true"><span class="octicon octicon-link"></span></a>registerRemote</h2>

<p>The method allows to agree getting video stream from a particular user.</p>

<p><strong>Gets a parameters list:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td>String</td>
<td>uid</td>
<td>Specifies the ID of the user who agrees to receive a video stream.</td>
</tr>
</tbody></table>

<p><strong>Return a value:</strong> no result.</p>

<h2><a id="user-content-unregisterremote" class="anchor" href="#unregisterremote" aria-hidden="true"><span class="octicon octicon-link"></span></a>unregisterRemote</h2>

<p>The method allows to stop receive a video stream from a particular user.</p>

<p><strong>Gets a parameters list:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td><strong>String</strong></td>
<td>uid</td>
<td>Specifies the user ID from which prohibits receive a video stream.</td>
</tr>
</tbody></table>

<p><strong>Return a value:</strong> no result.</p>

<h2><a id="user-content-getdevicelist" class="anchor" href="#getdevicelist" aria-hidden="true"><span class="octicon octicon-link"></span></a>getDeviceList</h2>

<p>The method allows to get a list all of cameras on device.</p>

<p><strong>Gets a parameters list:</strong> without parameters.</p>

<p><strong>Return a value:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td><code>Array&lt;IDevice&gt;</code></td>
<td>----</td>
<td>Returns array all of cameras on device.</td>
</tr>
</tbody></table>

<p> </p>

<h2><a id="user-content-geteffectlist" class="anchor" href="#geteffectlist" aria-hidden="true"><span class="octicon octicon-link"></span></a>getEffectList</h2>

<p>The method allows to get available effect list for video.</p>

<p><strong>Gets a parameters list:</strong> without parameters.</p>

<p><strong>Return a value:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td><code>Array&lt;IEffect&gt;</code></td>
<td>----</td>
<td>Returns array all available effects for video.</td>
</tr>
</tbody></table>

<h2><a id="user-content-sizetoresolutionlevel" class="anchor" href="#sizetoresolutionlevel" aria-hidden="true"><span class="octicon octicon-link"></span></a>sizeToResolutionLevel</h2>

<p>The method allows to get the resolution level from size of video.</p>

<p><strong>Gets a parameters list:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td>int</td>
<td>width</td>
<td>This is a width of video.</td>
</tr>
<tr>
<td>int</td>
<td>height</td>
<td>This is a height of video.</td>
</tr>
</tbody></table>

<p><strong>Return a value:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td>VideoController.ResolutionLevel</td>
<td>----</td>
<td>Returns an enum of resolution level.</td>
</tr>
</tbody></table>

<h2><a id="user-content-videocontrollerlistener" class="anchor" href="#videocontrollerlistener" aria-hidden="true"><span class="octicon octicon-link"></span></a>VideoControllerListener</h2>

<h3><a id="user-content-remotevideostate" class="anchor" href="#remotevideostate" aria-hidden="true"><span class="octicon octicon-link"></span></a>RemoteVideoState</h3>

<p>The enum allows to get a different a status from the outside incoming video.</p>

<p><strong>Parameters list:</strong></p>

<table><thead>
<tr>
<th>Item</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td>RVS_Started</td>
<td>Remote video started.</td>
</tr>
<tr>
<td>RVS_Stopped</td>
<td>Remote video stopped.</td>
</tr>
<tr>
<td>RVS_Paused</td>
<td>Remote video paused by QOS/hold.</td>
</tr>
<tr>
<td>RVS_Resumed</td>
<td>Remote video resumed by QOS.</td>
</tr>
</tbody></table>

<h3><a id="user-content-onremotevideostatechanged" class="anchor" href="#onremotevideostatechanged" aria-hidden="true"><span class="octicon octicon-link"></span></a>onRemoteVideoStateChanged</h3>

<p>The method allows to receive an event listener, when remote video state has been changed.</p>

<p><strong>Gets a parameters list:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td>String</td>
<td>uid</td>
<td>This is a user id of remote video.</td>
</tr>
<tr>
<td>RemoteVideoState</td>
<td>state</td>
<td>This is new remote video state.</td>
</tr>
<tr>
<td>int</td>
<td>width</td>
<td>This is a width resolution of video.</td>
</tr>
<tr>
<td>int</td>
<td>height</td>
<td>This is a height resolution of video.</td>
</tr>
<tr>
<td>sdk_error</td>
<td>error</td>
<td>This is an error code about changing in conference.</td>
</tr>
</tbody></table>

<p><strong>Return a value:</strong> no result.  </p>

<h3><a id="user-content-oncamerastatechanged" class="anchor" href="#oncamerastatechanged" aria-hidden="true"><span class="octicon octicon-link"></span></a>onCameraStateChanged</h3>

<p>The method allows to get an event listener, when camera state has been exchanged.</p>

<p><strong>Gets a parameters list:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td>boolean</td>
<td>state</td>
<td>This is new camera state (ON/OFF).</td>
</tr>
<tr>
<td>String</td>
<td>deviceId</td>
<td>This is a device ID.</td>
</tr>
<tr>
<td>int</td>
<td>width</td>
<td>This is a width resolution of video.</td>
</tr>
<tr>
<td>int</td>
<td>height</td>
<td>This is a height resolution of video.</td>
</tr>
<tr>
<td>int</td>
<td>fps</td>
<td>This is a Frames per Second.</td>
</tr>
<tr>
<td>sdk_error</td>
<td>error</td>
<td>This is an error code about changing in conference.</td>
</tr>
</tbody></table>

<p><strong>Return a value:</strong> no result.</p>

<h3><a id="user-content-ontransmitstatechanged" class="anchor" href="#ontransmitstatechanged" aria-hidden="true"><span class="octicon octicon-link"></span></a>onTransmitStateChanged</h3>

<p>The method allows to get an event listener, when video transmit state has been exchanged.</p>

<p><strong>Gets a parameters list:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td>boolean</td>
<td>state</td>
<td>This is new video transmit state (ON/OFF).</td>
</tr>
<tr>
<td>sdk_error</td>
<td>error</td>
<td>This is an error code about changing in conference.</td>
</tr>
</tbody></table>

<p><strong>Return a value:</strong> no result.  </p>

<h3><a id="user-content-onvideopreviewstatechanged" class="anchor" href="#onvideopreviewstatechanged" aria-hidden="true"><span class="octicon octicon-link"></span></a>onVideoPreviewStateChanged</h3>

<p>The method allows to get an event listener, when preview video state has been exchanged.</p>

<p><strong>Gets a parameters list:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td>boolean</td>
<td>state</td>
<td>This is new preview video state (ON/OFF).</td>
</tr>
<tr>
<td>sdk_error</td>
<td>error</td>
<td>This is an error code about changing in conference.</td>
</tr>
</tbody></table>

<p><strong>Return a value:</strong> no result.</p>

<h3><a id="user-content-oncamerachanged" class="anchor" href="#oncamerachanged" aria-hidden="true"><span class="octicon octicon-link"></span></a>onCameraChanged</h3>

<p>The method allows to get an event listener, when active device has been exchanged.</p>

<p><strong>Gets a parameters list:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td>String</td>
<td>deviceId</td>
<td>This is camera device ID.</td>
</tr>
<tr>
<td>sdk_error</td>
<td>errorCode</td>
<td>This is an error code about changing in conference.</td>
</tr>
</tbody></table>

<p><strong>Return a value:</strong> no result.</p>

<h1><a id="user-content-videodevice" class="anchor" href="#videodevice" aria-hidden="true"><span class="octicon octicon-link"></span></a>VideoDevice</h1>

<h2><a id="user-content-getavailableresolutions-1" class="anchor" href="#getavailableresolutions-1" aria-hidden="true"><span class="octicon octicon-link"></span></a>getAvailableResolutions</h2>

<p>The method allows to get a list available the resolutions of video.</p>

<p><strong>Gets a parameters list:</strong> without parameters.</p>

<p><strong>Return a value:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td>ArrayList&lt;VideoController.ResolutionLevel&gt;</td>
<td>----</td>
<td>Returns a list resolutions.</td>
</tr>
</tbody></table>

<h2><a id="user-content-isresolutionsupported-1" class="anchor" href="#isresolutionsupported-1" aria-hidden="true"><span class="octicon octicon-link"></span></a>isResolutionSupported</h2>

<p>The method allows to check, if this a resolution level is supported.</p>

<p><strong>Gets a parameters list:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td>VideoController.ResolutionLevel</td>
<td>level</td>
<td>This is a resolution for checking.</td>
</tr>
</tbody></table>

<p><strong>Return a value:</strong></p>

<table><thead>
<tr>
<th>Type</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td>boolean</td>
<td>----</td>
<td>Returns boolean value, If there is support for the requested resolution.</td>
</tr>
</tbody></table>
</article>
  </div>

</div>

<a href="#jump-to-line" rel="facebox[.linejump]" data-hotkey="l" style="display:none">Jump to Line</a>
<div id="jump-to-line" style="display:none">
  <!-- </textarea> --><!-- '"` --><form accept-charset="UTF-8" action="" class="js-jump-to-line-form" method="get"><div style="margin:0;padding:0;display:inline"><input name="utf8" type="hidden" value="&#x2713;" /></div>
    <input class="linejump-input js-jump-to-line-field" type="text" placeholder="Jump to line&hellip;" aria-label="Jump to line" autofocus>
    <button type="submit" class="btn">Go</button>
</form></div>

        </div>
      </div>
      <div class="modal-backdrop"></div>
    </div>
  </div>


    </div>

      <div class="container">
  <div class="site-footer" role="contentinfo">
    <ul class="site-footer-links right">
        <li><a href="https://status.github.com/" data-ga-click="Footer, go to status, text:status">Status</a></li>
      <li><a href="https://developer.github.com" data-ga-click="Footer, go to api, text:api">API</a></li>
      <li><a href="https://training.github.com" data-ga-click="Footer, go to training, text:training">Training</a></li>
      <li><a href="https://shop.github.com" data-ga-click="Footer, go to shop, text:shop">Shop</a></li>
        <li><a href="https://github.com/blog" data-ga-click="Footer, go to blog, text:blog">Blog</a></li>
        <li><a href="https://github.com/about" data-ga-click="Footer, go to about, text:about">About</a></li>
        <li><a href="https://github.com/pricing" data-ga-click="Footer, go to pricing, text:pricing">Pricing</a></li>

    </ul>

    <a href="https://github.com" aria-label="Homepage">
      <span class="mega-octicon octicon-mark-github" title="GitHub"></span>
</a>
    <ul class="site-footer-links">
      <li>&copy; 2015 <span title="0.08193s from github-fe135-cp1-prd.iad.github.net">GitHub</span>, Inc.</li>
        <li><a href="https://github.com/site/terms" data-ga-click="Footer, go to terms, text:terms">Terms</a></li>
        <li><a href="https://github.com/site/privacy" data-ga-click="Footer, go to privacy, text:privacy">Privacy</a></li>
        <li><a href="https://github.com/security" data-ga-click="Footer, go to security, text:security">Security</a></li>
        <li><a href="https://github.com/contact" data-ga-click="Footer, go to contact, text:contact">Contact</a></li>
        <li><a href="https://help.github.com" data-ga-click="Footer, go to help, text:help">Help</a></li>
    </ul>
  </div>
</div>



    
    
    

    <div id="ajax-error-message" class="flash flash-error">
      <span class="octicon octicon-alert"></span>
      <button type="button" class="flash-close js-flash-close js-ajax-error-dismiss" aria-label="Dismiss error">
        <span class="octicon octicon-x"></span>
      </button>
      Something went wrong with that request. Please try again.
    </div>


      <script crossorigin="anonymous" integrity="sha256-+Ec97OckLaaiDVIxNjSIGzl1xSzrqh5sOBV8DyYYVpE=" src="https://assets-cdn.github.com/assets/frameworks-f8473dece7242da6a20d52313634881b3975c52cebaa1e6c38157c0f26185691.js"></script>
      <script async="async" crossorigin="anonymous" integrity="sha256-aT8ZvOWj5pZ0QHLUJNNitxaHedaBZP70Hli0Mt9E1Kg=" src="https://assets-cdn.github.com/assets/github-693f19bce5a3e696744072d424d362b7168779d68164fef41e58b432df44d4a8.js"></script>
      
      
    <div class="js-stale-session-flash stale-session-flash flash flash-warn flash-banner hidden">
      <span class="octicon octicon-alert"></span>
      <span class="signed-in-tab-flash">You signed in with another tab or window. <a href="">Reload</a> to refresh your session.</span>
      <span class="signed-out-tab-flash">You signed out in another tab or window. <a href="">Reload</a> to refresh your session.</span>
    </div>
  </body>
</html>


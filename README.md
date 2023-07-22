<!DOCTYPE html>
<html class="loading" lang="en" data-textdirection="ltr">
<!-- BEGIN: Head-->

<head>
    <meta http-equiv="Content-Type" content="text/html; charset=UTF-8"> 
    <title>Noupia - Edit {{ $edit['name'] }}'s' Account Info</title>
    <!--------- styles here --------->
    @load('inc/favicon.php')
    <link href="https://fonts.googleapis.com/css?family=Montserrat:300,400,500,600" rel="stylesheet">
 
    <!-- BEGIN: Vendor CSS-->
    <link rel="stylesheet" type="text/css" href="/public/vuexy/app-assets/vendors/css/vendors.min.css">
    <link rel="stylesheet" type="text/css" href="/public/vuexy/app-assets/css/plugins/forms/validation/form-validation.css">
    <link rel="stylesheet" type="text/css" href="/public/vuexy/app-assets/vendors/css/forms/select/select2.min.css">
    <link rel="stylesheet" type="text/css" href="/public/vuexy/app-assets/vendors/css/pickers/pickadate/pickadate.css">
    <!-- END: Vendor CSS-->

    <!-- BEGIN: Theme CSS-->
    <link rel="stylesheet" type="text/css" href="/public/vuexy/app-assets/css/bootstrap.css">
    <link rel="stylesheet" type="text/css" href="/public/vuexy/app-assets/css/bootstrap-extended.css">
    <link rel="stylesheet" type="text/css" href="/public/vuexy/app-assets/css/colors.css">
    <link rel="stylesheet" type="text/css" href="/public/vuexy/app-assets/css/components.css">
    <link rel="stylesheet" type="text/css" href="/public/vuexy/app-assets/css/themes/dark-layout.css">
    <link rel="stylesheet" type="text/css" href="/public/vuexy/app-assets/css/themes/semi-dark-layout.css">

    <!-- BEGIN: Page CSS-->
    <link rel="stylesheet" type="text/css" href="/public/vuexy/app-assets/css/core/menu/menu-types/horizontal-menu.css">
    <link rel="stylesheet" type="text/css" href="/public/vuexy/app-assets/css/core/colors/palette-gradient.css">
    <link rel="stylesheet" type="text/css" href="/public/vuexy/app-assets/css/pages/app-user.css">
    <!-- END: Page CSS-->

    <!-- BEGIN: Custom CSS-->
    <link rel="stylesheet" type="text/css" href="/public/vuexy/assets/css/style.css">
    <!-- END: Custom CSS-->
    <style>
        strong{
            color: #212121!important;
        }
    </style>
    <!---->
</head>
<!-- END: Head-->

<!-- BEGIN: Body-->

<body class="horizontal-layout horizontal-menu 2-columns  navbar-floating footer-static  " data-open="hover" data-menu="horizontal-menu" data-col="2-columns">

    <!-- BEGIN: Header-->
    
    @load('inc/nav.php')
 
    <!-- END: Header-->


    <!-- BEGIN: Main Menu-->
    
    @load('inc/topnav.php')

    <!-- END: Main Menu-->

    <!-- BEGIN: Content-->


    <!-- add div with class .app-content here -->

<!-- BEGIN: Content-->
    <div class="app-content content">
        <div class="content-overlay"></div>
        <div class="header-navbar-shadow"></div>
        <div class="content-wrapper">
            <div class="content-header row">
            </div>
            <div class="content-body">
                <!-- users edit start -->
                <section class="users-edit">
                    <div class="card">
                        <div class="card-content">
                            <div class="card-body">
                                <ul class="nav nav-tabs mb-3" role="tablist">
                                    <li class="nav-item">
                                        <a class="nav-link d-flex align-items-center 
                                               {% if ( !isset($_GET['document']) && !isset($_GET['logs']) && !isset($_GET['information']) ): %}
                                                   active
                                               {% endif; %}
                                            " id="account-tab" data-toggle="tab" href="#account" aria-controls="account" role="tab" aria-selected="true">
                                            <i class="feather icon-user mr-25"></i><span class="d-none d-sm-block">{! $lang['account'] !}</span>
                                        </a>
                                    </li>
                                    <li class="nav-item">
                                        <a class="nav-link d-flex align-items-center 
                                               {% if ( isset($_GET['information']) ): %}
                                                   active
                                               {% endif; %}
                                               " id="information-tab" data-toggle="tab" href="#information" aria-controls="information" role="tab" aria-selected="false">
                                            <i class="feather icon-info mr-25"></i><span class="d-none d-sm-block">{! $lang['information'] !}</span>
                                        </a>
                                    </li>
                                    <li class="nav-item">
                                        <a class="nav-link d-flex align-items-center
                                               {% if ( isset($_GET['document']) ): %}
                                                   active
                                               {% endif; %}
                                            " id="social-tab" data-toggle="tab" href="#social" aria-controls="social" role="tab" aria-selected="false">
                                            <i class="feather icon-file-minus mr-25"></i>
                                            <span class="d-none d-sm-block">
                                                Compliance  
                                            </span>
                                        </a>
                                    </li>
                                    <li class="nav-item">
                                        <a class="nav-link d-flex align-items-center" id="transactions_-tab" data-toggle="tab" href="#transactions_" aria-controls="social" role="tab" aria-selected="false">
                                            <i class="feather icon-bar-chart-2 mr-25"></i><span class="d-none d-sm-block">{! $lang['transactions'] !}</span>
                                        </a>
                                    </li>
                                    <li class="nav-item">
                                        <a class="nav-link d-flex align-items-center" id="history-tab" data-toggle="tab" href="#history" aria-controls="social" role="tab" aria-selected="false">
                                            <i class="feather icon-pie-chart mr-25"></i><span class="d-none d-sm-block"> {! $lang['history'] !} </span>
                                        </a>
                                    </li>
                                    <li class="nav-item">
                                        <a class="nav-link d-flex align-items-center" id="activities-tab" data-toggle="tab" href="#activities" aria-controls="social" role="tab" aria-selected="false">
                                            <i class="feather icon-loader mr-25"></i><span class="d-none d-sm-block">{! $lang['activities'] !}</span>
                                        </a>
                                    </li>
                                    <li class="nav-item">
                                        <a class="nav-link d-flex align-items-center" id="behaviour-tab" data-toggle="tab" href="#behaviours" aria-controls="social" role="tab" aria-selected="false">
                                            <i class="feather icon-award mr-25"></i><span class="d-none d-sm-block">
                                                Social Credit
                                            </span>
                                        </a>
                                    </li>
                                    <li class="nav-item">
                                        <a onclick="window.location.href=`/users?edit={{ $edit['id'] }}&logs`" 
                                            class="nav-link d-flex align-items-center
                                                {% if ( isset($_GET['logs']) ): %}
                                                   active
                                                {% endif; %}
                                            " id="errors-tab" data-toggle="tab" href="#errors" role="tab" aria-selected="false" dhref="/users?edit={{ $edit['id'] }}&logs">
                                            <i class="feather icon-alert-triangle mr-25"></i><span class="d-none d-sm-block">
                                                System Logs
                                            </span>
                                        </a>
                                    </li>
                                    {% if (count($banks) > 0): %}
                                    <li class="nav-item">
                                        <a class="nav-link d-flex align-items-center" id="behaviour-tab" data-toggle="tab" href="#bankaccounts" aria-controls="social" role="tab" aria-selected="false">
                                            <i class="feather icon-hash mr-25"></i><span class="d-none d-sm-block">
                                                Bank Accounts
                                            </span>
                                        </a>
                                    </li>
                                    {% endif; %}
                                </ul>
                                <div class="tab-content">
                                    <div class="tab-pane 
                                        {% if ( !isset($_GET['document']) && !isset($_GET['logs']) && !isset($_GET['information']) ): %}
                                            active
                                        {% endif; %}
                                    " id="account" aria-labelledby="account-tab" role="tabpanel">
                                        <!-- users edit media object start -->
                                        <div class="media mb-2">
                                            <div class="mr-2 my-25" style="position: relative;"> 
                                                {% if (@count($unread) > 0): %}
                                                    <div style="color: white;background:#f75a5b;border-radius:50px;width:21px;height:21px;
                                                        position:absolute;top:-8px;right:-8px;">
                                                        <center>{{ count($unread) > 9 ? '9+' : count($unread) }}</center>
                                                    </div>
                                                {% endif; %}
                                                <img src="{{ $edit['avtr'] }}" alt="users avatar"
                                                    class="users-avatar-shadow rounded" height="90" width="90"
                                                    style="border: 0px solid #039be5;border-radius:90px!important;">
                                            </div>
                                            <div class="media-body mt-50">
                                                <h4 class="media-heading">  
                                                    <a href="/users?edit={{ $edit['id'] }} ">
                                                       {% if ($edit['noupia_plus'] > 0): %}
                                                            <i class="feather icon-plus {{ $edit['noupia_plus'] > time() ? 'text-primary' : 'text-danger' }}"></i>
                                                       {% endif; %}
                                                       {{ $edit['name'] }} 
                                                    </a> 
                                                    <img style="margin-bottom: 4px;" width="25" 
                                                        src="https://flagcdn.com/{{ strtolower($edit['country_code']) }}.svg">
                                                </h4>
                                                {% if ($edit['is_birthday'] == 'yes'): %}

                                                  🎉🎉🎉🎂 Celebrating {{ $edit['gender'] == 'F' ? 'her' : 'his' }} birthday today.

                                                {% endif; %}
                                               <!-- <div class="col-12 d-flex mt-1 px-0">
                                                    <a href="#" class="btn btn-primary d-none d-sm-block mr-75">Change</a>
                                                    <a href="#" class="btn btn-primary d-block d-sm-none mr-75"><i class="feather icon-edit-1"></i></a>
                                                    <a href="#" class="btn btn-outline-danger d-none d-sm-block">Remove</a>
                                                    <a href="#" class="btn btn-outline-danger d-block d-sm-none"><i class="feather icon-trash-2"></i></a>
                                                </div> --> 
                                                <p class=" {{ $edit['score'] >= 1000 ? 'text-success' : 'text-danger' }} "> {{ number_format( $edit['score']) }} Points  </p>   
                                                <div class="action-btns">
                                                    <div class="btn-dropdown ">
                                                        <div class="btn-group dropdown actions-dropodown">
                                                            <button style="border: none;margin-left:-8px;" type="button" class="dropdown-toggle bg-white" data-toggle="dropdown"> Actions </button>
                                                            <div class="dropdown-menu" x-placement="bottom-start" style="position: absolute; will-change: transform; top: 0px; left: 0px; transform: translate3d(0px, 36px, 0px);">
                                                                <a class="dropdown-item" href="/assistance?id={{$edit['id']}}"><i class="feather icon-message-square"></i>Chat as Noupia</a>
                                                                <a class="dropdown-item" href="/assistance2?id={{$edit['id']}}"><i class="feather icon-message-circle"></i>Chat as {{ $_SESSION['staffname'] }}</a> 
                                                                <a class="dropdown-item" href="#?grade" onclick="gradeUser({ id : '{{ $edit['id'] }}', name : '{{ $edit['name'] }}' })" 
                                                                    data-i18n="Synchronize"><i class="feather icon-pie-chart"></i> Credit score </a>
                                                                <a class="dropdown-item" href="#?report" onclick="generateReport({ language : '{{ $edit['language'] }}', id : '{{ $edit['id'] }}', name : '{{ $edit['name'] }}', country : '{{ $edit['country_code'] }}' })" 
                                                                    data-i18n="Synchronize"><i class="feather icon-file-text"></i> Generate report </a>
                                                                <a class="dropdown-item" href="#?activity" onclick="recordActivity({ id : '{{ $edit['id'] }}', name : '{{ $edit['name'] }}', country : '{{ $edit['country_code'] }}' })" 
                                                                    data-i18n="Synchronize"><i class="feather icon-loader"></i>  Record activity </a> 
                                                                <a class="dropdown-item" href="#?debit" onclick="debitUser({ id : '{{ $edit['id'] }}', name : '{{ $edit['name'] }}' })" 
                                                                    data-i18n="Synchronize"><i class="feather icon-dollar-sign"></i> Bill user </a>
                                                            </div>
                                                        </div>
                                                    </div>
                                                </div>
                                            </div>
                                        </div>
                                        <!-- users edit media object ends -->
                                        <!-- users edit account form start -->
                                        <form novalidate method="post" action="/editu">
                                            <input type="hidden" name="editaccount">
                                            <input type="hidden" name="userid" value="{{ $edit['id'] }}"> 
                                            <div class="row"> 
                                                <div class="col-12 col-sm-6 col-lg-4"> 
                                                    <div class="row"> 
                                                        <div class="controls col-12 col-lg-6 col-md-12">
                                                            <label>
                                                                📞 {! $lang['phone'] !}
                                                                <span class="copy" data-clipboard-text="{{ $edit['phone'] }}" data-clipboard-short></span>
                                                            </label>
                                                            <input type="text" class="form-control text-primary" placeholder="" name="phone" value="{{ $edit['phone'] }}" required>
                                                        </div> 
                                                        <div class="form-group col-12 col-lg-6 col-md-12">
                                                            <div class="controls">
                                                                <label>💵 {! $lang['balance'] !}</label>
                                                                <input type="text" class="form-control bg-primary text-white" placeholder="" readonly 
                                                                    value="{{ @number_format(@$edit['balance']) }} CFA" >
                                                            </div>
                                                            <span class="text-primary" style="font-size: 13px;">
                                                             💰 Savings {{ number_format($edit['savings']) }} CFA
                                                            </span>
                                                        </div>
                                                    </div> 
                                                    <div class="row">   
                                                        <div class="controls col-12 col-lg-6 col-md-12">
                                                            <label>{{ $edit['feeling2'] }} Feeling </label>
                                                            <input type="text" class="form-control" placeholder="Sentiment" readonly
                                                                   value="{{ $edit['feeling'] }}">
                                                        </div> 
                                                        <div class="form-group col-12 col-lg-6 col-md-12">
                                                            <label>❌ FAILED PURCHASES</label>
                                                            <input type="text" class="form-control no-border  {{ $edit['failed_purchases'] > 20 ? 'text-danger text-white' : 'text-primary' }}" 
                                                             style="border:0px;" placeholder="" readonly value="{{ $edit['failed_purchases'] }}" >
                                                        </div>
                                                    </div>
                                                    <div class="row"> 
                                                        <div class="form-group col-12 col-lg-3 col-md-12">
                                                            <div class="controls">
                                                                <label>🔑 {! $lang['user_id'] !}</label>
                                                                <input readonly type="number" class="form-control" 
                                                                    value="{{ $edit['id'] }}">
                                                            </div>
                                                        </div>
                                                        
                                                        {% if ($role == 'noupia' or true): %} 
                                                            <div class="controls col-12 col-lg-4 col-md-12">
                                                                <label>✅ Profit Generated </label>
                                                                <input type="text" class="form-control text-success" readonly value="{{ $edit['profit'] > 0 ? '+' : '' }}{{ number_format($edit['profit']) }} CFA">
                                                            </div> 
                                                        {% endif; %} 
                                                        <div class="controls col-12 col-lg-5 col-md-12">
                                                            <label>📊 Transaction volume </label>
                                                            <input type="text" class="form-control text-warning" readonly value="{{ $edit['t_volume'] > 0 ? '+' : '' }}{{ number_format($edit['t_volume']) }} CFA">
                                                        </div>
                                                    </div>
                                                    <div class="form-group"> 
                                                        <div class="controls">
                                                            <label>🤵🏼 {! $lang['legal_name'] !} 
                                                                <span class="copy" data-clipboard-text="{{ $edit['name'] }}" data-clipboard-short></span>
                                                            </label>
                                                            <input name="name" type="text" class="form-control" id="user-legal-name"
                                                                   placeholder="Name" value="{{ $edit['name'] }}" 
                                                                   required >
                                                        </div>
                                                    </div>
                                                    <div class="form-group row">
                                                        <div class="controls col-6">
                                                            <label>🚹 {! $lang['gender'] !}</label> 
                                                            <select class="form-control" name="gender">
                                                                <option value="no" {{ $edit['gender'] == 'NONE' ? 'selected' : '' }} >NONE</option>
                                                                <option value="M" {{ $edit['gender'] == 'M' ? 'selected' : '' }} >MALE</option>
                                                                <option value="F" {{ $edit['gender'] == 'F' ? 'selected' : '' }}>FEMALE</option>
                                                            </select>
                                                        </div>
                                                        <div class="controls col-6">
                                                            <label>
                                                                📧 {! $lang['e_mail'] !}
                                                                <span class="copy" data-clipboard-text="{{ $edit['email'] }}" data-clipboard-short></span>
                                                            </label>
                                                            <input type="email" class="form-control" placeholder="Email" name="email"
                                                                   value="{{ $edit['email'] }}" required> 
                                                            <a href="#resend" class="data-resend-email-confirmation"
                                                            data-email="{{ $edit['email'] }}" 
                                                            data-token="{{ $edit['email_token'] }}"
                                                            data-language="{{ $edit['language'] }}"
                                                            data-name="{{ $edit['name'] }}"
                                                            data-account="{{ $edit['account_number'] }}"
                                                            data-id="{{ $edit['id'] }}"
                                                            >Resend confirmation</a>
                                                        </div> 
                                                    </div>
                                                    <div class="form-group row">
                                                        <div class="controls col-6">
                                                            <label>👜 Listed Products</label>
                                                            <input disabled type="text" class="form-control" 
                                                                value="{{ $edit['partner_products'] }}" 
                                                                placeholder="">
                                                        </div>
                                                        <div class="controls col-6">
                                                            <label>🚩 Card Partner</label>
                                                            <input disabled type="text" class="form-control" 
                                                                value="{{ $edit['partner_card'] }}" 
                                                                placeholder="">
                                                        </div>
                                                    </div> 
                                                    <div class="form-group row">
                                                        <div class="controls col-6">
                                                            <label>🚩 Tip Partner</label>
                                                            <input disabled type="text" class="form-control" 
                                                                value="{{ $edit['partner_tip'] }}" 
                                                                placeholder="">
                                                        </div>
                                                        <div class="controls col-6">
                                                            <label>👨🏽‍💻 Developer</label>
                                                            <input disabled type="text" class="form-control" 
                                                                value="{{ $edit['partner_developer'] }}" 
                                                                placeholder="">
                                                        </div>
                                                    </div> 
                                                    <div class="form-group"> 
                                                        <!--<a href="/assistance?id={{$edit['id']}}" 
                                                            target="_blank" class="btn btn-primary glow ">
                                                           <i class="feather icon-message-square"></i>    
                                                          Chat
                                                        </a>-->
                                                        <div class="action-btns">
                                                            <div class="btn-dropdown ">
                                                                <div class="btn-group dropdown actions-dropodown">
                                                                    <button type="button" 
                                                                        class="btn btn-success glow dropdown-toggle waves-effect waves-light" 
                                                                        data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
                                                                    Chat as                                                        
                                                                    </button>
                                                                    <div class="dropdown-menu" x-placement="bottom-start" style="position: absolute; will-change: transform; top: 0px; left: 0px; transform: translate3d(0px, 36px, 0px);">
                                                                        <a class="dropdown-item" href="/assistance?id={{$edit['id']}}"><i class="feather icon-message-square"></i> Noupia</a>
                                                                        <a class="dropdown-item" href="/assistance2?id={{$edit['id']}}"><i class="feather icon-user"></i> {{ $_SESSION['staffname'] }}</a> 
                                                                    </div>
                                                                </div>
                                                                &nbsp;&nbsp;&nbsp;&nbsp; 
                                                                <div class="btn-group dropdown actions-dropodown">
                                                                    <button type="button" 
                                                                        class="btn btn-danger glow dropdown-toggle waves-effect waves-light" 
                                                                        data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
                                                                        <i class="feather icon-target"></i> One Signal                                                      
                                                                    </button>
                                                                    <div class="dropdown-menu" x-placement="bottom-start" style="position: absolute; will-change: transform; top: 0px; left: 0px; transform: translate3d(0px, 36px, 0px);">
                                                                        <a onclick="window.sendOneSignal({ player_id : '{{ $edit['player_id'] }}', name : '{{ $edit['name'] }}', id : '{{ $edit['id'] }}', type : 'custom' })" class="dropdown-item" >
                                                                        <i class="feather icon-message-circle"></i> Custom Message</a>

                                                                        <a onclick="window.sendOneSignal({ player_id : '{{ $edit['player_id'] }}', name : '{{ $edit['name'] }}', id : '{{ $edit['id'] }}', type : 'welcome' })" class="dropdown-item" >
                                                                        <i class="feather icon-check-circle"></i> Welcome Message</a>

                                                                        <a onclick="window.sendOneSignal({ player_id : '{{ $edit['player_id'] }}', name : '{{ $edit['name'] }}', id : '{{ $edit['id'] }}', type : 'uploadID' })" class="dropdown-item" >
                                                                        <i class="feather icon-file"></i> Upload ID</a>
                                                                    </div>
                                                                </div>
                                                            </div>
                                                        </div>  
                                                        <br>
                                                        <br>
                                                    </div> 
                                                </div>
                                                <div class="col-12 col-sm-6 col-lg-4"> 
                                                    <div class="row">
                                                       <div class="form-group col-12 col-lg-6 col-md-12">
                                                           <label>🆔 {! $lang['identity_status'] !}</label>
                                                            <select class="form-control" name="id_verified">
                                                                <option value="no" {{ $edit['id_verified'] == 'no' ? 'selected' : '' }} >NOT VERIFIED</option>
                                                                <option value="yes" {{ $edit['id_verified'] == 'yes' ? 'selected' : '' }}>VERIFIED</option>
                                                            </select> 
                                                       </div>
                                                       <div class="form-group col-12 col-lg-6 col-md-12">
                                                            <label>🤵🏼 {! $lang['account_status'] !}</label>
                                                            <select class="form-control" name="status">
                                                                <option value="pending" {{ $edit['account_status'] == 'pending' ? 'selected' : '' }}>Pending Verification</option>
                                                                <option value="active" {{ $edit['account_status'] == 'active' ? 'selected' : '' }} >Active</option>
                                                                <option value="suspended" {{ $edit['account_status'] == 'suspended' ? 'selected' : '' }}>Suspended</option> 
                                                                <option value="disabled" {{ $edit['account_status'] == 'disabled' ? 'selected' : '' }}>Disabled</option> 
                                                            </select>
                                                       </div> 
                                                    </div>
                                                    {% if ( $edit['cards'] > 0 and $edit['date_created'] < 1658389440 ): %}
                                                    <div class="form-group">
                                                        <label> CARD BALANCE REFUNDED </label>
                                                        <input type="text" class="form-control {{ $edit['refunded'] == 'yes' ? 'text-success' : 'text-danger' }}" 
                                                            placeholder="" readonly value="{{ strtoupper($edit['refunded']) }}" >
                                                    </div>
                                                    {% endif; %}
                                                    <div class="row">
                                                       <div class="form-group col-12 col-lg-6 col-md-12">
                                                           <label>⬆️ User can withdraw</label>
                                                            <select class="form-control" name="can_withdraw">
                                                                <option value="no" {{ $edit['can_withdraw'] == 'no' ? 'selected' : '' }} >NO</option>
                                                                <option value="yes" {{ $edit['can_withdraw'] == 'yes' ? 'selected' : '' }}>YES</option>
                                                            </select> 
                                                       </div> 
                                                       <div class="form-group col-12 col-lg-6 col-md-12">
                                                           <label>↗️ User can transfer</label>
                                                            <select class="form-control" name="can_transfer">
                                                                <option value="no" {{ $edit['can_transfer'] == 'no' ? 'selected' : '' }} >NO</option>
                                                                <option value="yes" {{ $edit['can_transfer'] == 'yes' ? 'selected' : '' }}>YES</option>
                                                            </select> 
                                                       </div> 
                                                    </div> 
                                                    <div class="form-group  ">
                                                        <label>🔐 Encrypted PIN </label>
                                                        <input type="text" class="form-control" name="pin"
                                                            value="{{ $edit['pin'] }}" 
                                                            placeholder="">
                                                    </div>
                                                    {% if ($role == 'noupia' or true): %}
                                                    <div class="row form-group"> 
                                                        <div class="controls col-6 ">
                                                            <label> Change PIN? </label>
                                                            <select class="form-control" name="change_pin">
                                                                <option value="no" >NO</option>
                                                                <option value="yes">Yes</option>
                                                            </select>
                                                        </div> 
                                                        <div class="controls col-6">
                                                            <label>{! $lang['two_verification'] !}</label> 
                                                            <select class="form-control" name="2fauth">
                                                                <option value="off" {{ $edit['_2fauth'] == 'off' ? 'selected' : '' }}>OFF</option>
                                                                <option value="on" {{ $edit['_2fauth'] == 'on' ? 'selected' : '' }}>ON</option>
                                                            </select>
                                                        </div>
                                                    </div>
                                                    {% else: %}
                                                        <input type="hidden" name="change_pin" value="no">
                                                    {% endif; %}
                                                    <div class="form-group row">
                                                        <div class="controls col-6">
                                                            <label>🕘 {! $lang['registered'] !}</label>
                                                            <input readonly type="text" class="form-control" 
                                                                value="{{ @date('D, dS M Y - h:i a', $edit['date_created']) }}" 
                                                                placeholder="Date Registered">
                                                        </div>
                                                        <div class="controls col-6">
                                                            <label>⏳ {! $lang['became_active'] !}</label>
                                                            <input readonly type="text" class="form-control" 
                                                                value="{{ @date('D, dS M Y', @$active['date_created']) }}" 
                                                                placeholder="Date active">
                                                        </div>
                                                    </div> 
                                                    <div class="form-group row"> 
                                                        <div class="controls col-6">
                                                            <label>👨🏼 Age</label>
                                                            <input readonly type="text" class="form-control" 
                                                                value="{{ $edit['age'] }}" 
                                                                placeholder="Date Registered">
                                                        </div>
                                                        <div class="controls col-6">
                                                            <label>🎂 Birth year</label>
                                                            <input readonly type="text" class="form-control" 
                                                                value="{{ $edit['birth_year'] }}" 
                                                                placeholder="Date active">
                                                        </div>
                                                    </div>
                                                    <div class="form-group row">
                                                        <div class="controls col-6">
                                                            <label>📱 Last Device</label>
                                                            <input readonly type="text" class="form-control" 
                                                                value="{{ $edit['last_device'] }}" 
                                                                placeholder="Date Registered">
                                                        </div>
                                                        <div class="controls col-6">
                                                            <label>🔗 Last Page</label>
                                                            <input readonly type="text" class="form-control" 
                                                                value="{{ $edit['last_page'] }}" 
                                                                placeholder="Date Registered">
                                                        </div>
                                                    </div>
                                                    <div class="form-group justify-content-end mt-1"> 
                                                     
                                                        <a href="https://api.whatsapp.com/send?phone={{$edit['phone_code']}}{{$edit['phone']}}&text=Hello, {{ explode(' ', $edit['name'])[0] }}." 
                                                            target="_blank" class="btn_btn-primary_glow">
                                                          <i class="feather icon-share-2"></i>   WhatsApp {{ explode(' ', $edit['name'])[0] }}
                                                        </a> 
                                                    </div> 
                                                </div>
                                                <div class="col-12 col-sm-6 col-lg-4"> 
                                                    <div class="form-group row">
                                                        <div class="controls col-6">
                                                            <label>
                                                                🪪 Noupia ID
                                                                <span class="copy" data-clipboard-text="{{ $edit['account_number'] }}" data-clipboard-short></span>
                                                            </label>
                                                            <input readonly type="text" class="form-control" 
                                                                value="{{ strtoupper($edit['account_number']) }}" 
                                                                placeholder="">
                                                        </div> 
                                                        <div class="controls col-6">
                                                            <label>🔓 {! $lang['app_lock'] !}</label>
                                                            <input readonly type="text" class="form-control" 
                                                                value="{{ strtoupper($edit['app_lock']) }}" 
                                                                placeholder="">
                                                        </div> 
                                                    </div> 
                                                    <div class="row">
                                                        <div class="form-group col-12 col-lg-12 col-md-12">
                                                            <div class="controls">
                                                                <label for="user-comment">Write any comment about this Account</label>
                                                                <textarea class="form-control text-primary" name="comment" id="user-comment" rows="5">{{ $edit['comment'] }}</textarea>
                                                            </div>
                                                       </div>
                                                    </div>
                                                    <div class="form-group row">
                                                        <div class="controls col-6">
                                                            <label>💲 Cards balance</label>
                                                            <input readonly type="text" class="form-control" value="{{ $edit['cards_balance'] }} USD"  >
                                                        </div>
                                                        <div class="controls col-6">
                                                            <label>💳 {! $lang['no_of_cards'] !}</label>
                                                            <input readonly type="text" class="form-control" 
                                                                value="{{ count($cards) }}"  >
                                                        </div> 
                                                    </div>
                                                    <div class="form-group">
                                                        <label>📈 {! $lang['total_transaction'] !}</label>
                                                        <input readonly type="text" class="form-control" 
                                                               value="{{ number_format($edit['transactions']) }}+"  
                                                               placeholder="">
                                                    </div>
                                                    <div class="form-group">
                                                        <label>⌚ Last Seen</label> 
                                                        {% if( date('d-m-Y') == date('d-m-Y', $edit['last_online']) ): %}
                                                        <input readonly type="text" class="form-control bg-success text-white" 
                                                               value="Today at {{ date('h:i a', $edit['last_online']) }}">
                                                        {% else: %}
                                                           <input readonly type="text" class="form-control" 
                                                               value="{{ date('h:i a - D, dS M Y', $edit['last_online']) }}">
                                                        {% endif; %}
                                                    </div> 
                                                    <div class="form-group">
                                                        <label>🛡️ {! $lang['last_sign_in'] !}</label>
                                                        <input disabled type="text" class="form-control" 
                                                               value="{{ @date('D, dS M Y @ h:i a', $session['datecreated']) }}" 
                                                               placeholder="Last Login">
                                                    </div> 
                                                    <div class="row">
                                                        <div class="form-group col-12 col-lg-6 col-md-12">
                                                            <label>{! $lang['last_ip_address'] !}</label>
                                                            <input disabled type="text" class="form-control" 
                                                                value="{{ $edit['last_ip_address'] }}" 
                                                                placeholder="Last IP">
                                                        </div> 
                                                        <div class="form-group col-12 col-lg-6 col-md-12">
                                                            <label>🌄 Theme</label>
                                                            <input disabled type="text" class="form-control" value="{{ $edit['theme'] }}" placeholder="">
                                                        </div>
                                                    </div> 
                                                    <!--<div class="form-group row"> 
                                                        <div class="controls col-6">
                                                            <label>💬 Noupia Chat Enabled</label>
                                                            <input readonly type="text" class="form-control" 
                                                                value="{{ $edit['chat_on'] }}" 
                                                                placeholder="Date Registered">
                                                        </div>
                                                        <div class="controls col-6">
                                                            <label>🔍 Search Enabled</label>
                                                            <input readonly type="text" class="form-control" 
                                                                value="{{ $edit['search_on'] }}" 
                                                                placeholder="Date Registered">
                                                        </div>
                                                    </div>-->
                                                    <div class="form-group justify-content-end mt-1">
                                                        <button type="submit" class="btn btn-primary glow mb-1 mb-sm-0 mr-0 mr-sm-1">
                                                             <i class="feather icon-save"></i> {! $lang['save_changes'] !}
                                                        </button> 
                                                     </div>
                                                </div> 
                                            </div>
                                        </form>
                                        <!-- users edit account form ends -->
                                    </div>
                                    <div class="tab-pane
                                        {% if ( isset($_GET['information']) ): %}
                                            active
                                        {% endif; %}
                                    " id="information" aria-labelledby="information-tab" role="tabpanel">
                                        <!-- users edit Info form start -->
                                        <form novalidate method="post" action="/editu">
                                            <input type="hidden" name="editprofile">
                                            <input type="hidden" name="userid" value="{{ $edit['id'] }}">
                                            <div class="row mt-1">
                                                <div class="col-12 col-sm-6 col-lg-4">
                                                    <h5 class="mb-1"><i class="feather icon-user mr-25"></i>
                                                    {! $lang['about'] !} {{ $edit['name'] }}</h5> 
                                                    <div class="form-group row">
                                                        <div class="controls col-6">
                                                            <label>🌍 {! $lang['country'] !}</label>
                                                            <input type="hidden" value="{{ $edit['country_code'] }}">
                                                            <input type="text" class="form-control" name="country" 
                                                                   value="{{ $edit['country_code'] }}" placeholder="Country" 
                                                                   data-validation-required-message="User's country is required">
                                                        </div>
                                                        <div class="controls col-6">
                                                            <label>📲 Phone Code</label> 
                                                            <input type="text" class="form-control" name="phone_code" required minlength="2"
                                                                   value="{{ $edit['phone_code'] }}" placeholder="Phone code">
                                                        </div>
                                                    </div> 
                                                    <div class="form-group">
                                                        <div class="controls">
                                                            <label>🗺️ {! $lang['goe_details'] !}</label>
                                                            <textarea rows="5" disabled type="text" class="form-control" required placeholder="Website here..."   
                                                                      data-validation-required-message="This Website field is required"
                                                                      >{{ $edit['signup_useragent'] }} &nbsp;&nbsp;{! $lang['ip_address'] !}: {{ $edit['signup_ip_address'] }}</textarea>
                                                        </div>
                                                    </div>
                                                    <div class="form-group">
                                                        <div class="controls">
                                                            <label>🔴 {! $lang['one_signal'] !}
                                                            <span class="copy" data-clipboard-text="{{ $edit['player_id'] }}" data-clipboard-short></span>
                                                            </label> 
                                                            <input disabled type="text" class="form-control"  value="{{ $edit['player_id'] }}">
                                                        </div>
                                                    </div>
                                                    <div class="form-group">
                                                        <div class="controls">
                                                            <label>🎂 {! $lang['birth_date'] !}</label>
                                                            <input name="birth" type="text" 
                                                                   class="form-control   --birthdate-picker --picker__input --picker__input--active" 
                                                                   value="{{ $edit['dob']   }}" placeholder="DD-MM-YYYY" 
                                                                   data-validation-required-message="User date of birth is required">
                                                        </div>
                                                    </div>
                                                </div>
                                                <div class="col-12 col-sm-6 col-lg-4">
                                                    <h5 class="mb-1 mt-2 mt-sm-0"> &nbsp; </h5>
                                                    <div class="row">
                                                        <div class="form-group col-12">
                                                            <div class="controls">
                                                                <label>🏡 {! $lang['address'] !}</label>
                                                                <input name="address" disabled type="text" class="form-control" value="{{ $edit['address'] }}"  placeholder="Address Line 1" 
                                                                    ddata-validation-required-message="This Address field is required">
                                                            </div>
                                                        </div> 
                                                        <div class="form-group col-12 col-lg-6">
                                                            <div class="controls">
                                                                <label>🪧 {! $lang['postcode'] !}</label>
                                                                <input name="zip" disabled type="text" class="form-control"  placeholder="postcode" 
                                                                    value="000" ddata-validation-required-message="This Postcode field is required">
                                                            </div>
                                                        </div> 
                                                        <div class="form-group col-12 col-lg-6">
                                                            <div class="controls">
                                                                <label>🏢 {! $lang['city'] !}</label>
                                                                <input name="city" disabled type="text" class="form-control"  
                                                                    value="{{ $edit['city'] }}" ddata-validation-required-message="This Time Zone field is required">
                                                            </div>
                                                        </div> 
                                                        <div class="form-group col-12">
                                                            <div class="controls">
                                                                <label>🌐 {! $lang['language'] !}</label>
                                                                <input disabled type="text" class="form-control"   
                                                                    value="{{ strtoupper($edit['language']) }}" >
                                                            </div>
                                                        </div>
                                                        <div class="form-group col-12">
                                                            <div class="controls">
                                                                <label>♍ Zodiac sign</label>
                                                                <input disabled type="text" class="form-control"   
                                                                    value="{{ is_null($edit['zodiac']) ? 'NOT SET' : $edit['zodiac'] }}" >
                                                            </div>
                                                        </div>
                                                        <div class="form-group col-12">
                                                            <div class="controls">
                                                                <label>🗺️ Last known coordinates (Approx. ) </label>
                                                                <input disabled type="text" class="form-control"   
                                                                    value="{{ strtoupper($edit['coords']) }} | {{$edit['last_location']}}" >
                                                            </div>
                                                        </div>
                                                        <div class="form-group col-12">
                                                            <div class="controls">
                                                                <label>🧭 {! $lang['last_geo'] !}</label>
                                                                <textarea rows="5" disabled type="text" class="form-control" required placeholder="Website here..."   
                                                                        data-validation-required-message="This Website field is required"
                                                                        >{{ $edit['last_useragent'] }} &nbsp;&nbsp;{! $lang['ip_address'] !}: {{ $edit['last_ip_address'] }}</textarea>
                                                            </div>
                                                        </div> 
                                                    </div> 
                                                </div> 
                                                <div class="col-12 col-sm-6 col-lg-4">
                                                    <h5 class="mb-1 mt-2 mt-sm-0"> &nbsp; </h5>
                                                    <div class="row">
                                                        <div class="form-group col-12 col-lg-6">
                                                            <label>📶 
                                                                {! $lang['mtn_mobile'] !}
                                                                <span class="copy" data-clipboard-text="{{ $edit['momo_number'] }}" data-clipboard-short></span>
                                                            </label>
                                                            <input type="text" class="form-control" name="momo" value="{{ $edit['momo_number'] }}"   placeholder="">
                                                        </div>
                                                        <div class="form-group col-12 col-lg-6">
                                                            <label>📶 
                                                                {! $lang['orange_money'] !}
                                                                <span class="copy" data-clipboard-text="{{ $edit['orange_number'] }}" data-clipboard-short></span>
                                                            </label>
                                                            <input type="text" class="form-control" name="om" value="{{ $edit['orange_number'] }}"   placeholder="">
                                                        </div>



                                                        <div class="form-group col-12 col-lg-6">
                                                        {% if ( @$cards[0]['provider'] == 'sd' ): %}
                                                        <span >
                                                            <a class="text-success" href="https://noupia.com/stripe/?amount={{ @$cards[0]['balance'] }}&card_id={{ @$cards[0]['card_id'] }}&lang={{ $edit['language'] }}&email={{ $edit['email'] }}&user_id={{ $edit['id'] }}&noupia_id={{ $edit['account_number']}}&account_id={{ @$cards[0]['account_id'] }}" target="_blank">
                                                                Stripe Refund
                                                            </a>
                                                        </span>
                                                        {% endif; %}
                                                        <hr>
                                                        <label>
                                                            1st Card {{ @$cards[0]['masked_pan'] }} 
                                                            <span class="text-primary">{{ @strtoupper($cards[0]['type']) }}</span> 
                                                            <br>
                                                            <span class="color" style="font-size: 17px;">
                                                            {{ @strtoupper($cards[0]['cardholder']) }} 
                                                            </span>
                                                        </label>
                                                        <br>
                                                        Card ID <span class="copy" data-clipboard-text="{{ @$cards[0]['card_id'] }}" data-clipboard-short></span>
                                                        <input readonly type="text" class="form-control text-primary {{ @$cards[0]['status'] == 'blocked' ? 'bg-danger text-white'  : '' }}" 
                                                            value="{{ @$cards[0]['card_id'] }}"   placeholder="">
                                                        Account ID <span class="copy" data-clipboard-text="{{ @$cards[0]['account_id'] }}" data-clipboard-short></span>
                                                        <input readonly type="text" class="form-control text-primary" 
                                                            value="{{ @$cards[0]['account_id'] }}"   placeholder="">
                                                        </div>
                                                        <div class="form-group col-12 col-lg-6">
                                                            <label>
                                                                <span class="text-primary">
                                                                    {{ @strtoupper($cards[0]['provider']) }} 
                                                                </span>
                                                                 on
                                                                {{ date('dS M Y, h:i A', @$cards[0]['issued']) }}
                                                                <br>
                                                                <span class="color" style="font-size: 17px;">
                                                                {{ @strtoupper($cards[0]['status']) }} 
                                                                </span>
                                                            </label>
                                                            <input readonly type="text" class="form-control" 
                                                                value="{{ @round($cards[0]['balance'], 2) }}$ - {{ @strtoupper($cards[0]['type']) }} "   placeholder="">
                                                        </div>


                                                        <br><br><br><br><br><br>

                                                        <div class="form-group col-12 col-lg-6">
                                                            <label>
                                                                2nd Card {{ @$cards[1]['masked_pan'] }}
                                                                <span class="text-primary">{{ @strtoupper($cards[1]['type']) }}</span> 
                                                                <br>
                                                                <span class="color" style="font-size: 17px;">
                                                                {{ @strtoupper($cards[1]['cardholder']) }} 
                                                                </span>
                                                                <br> 
                                                            </label>
                                                            <br>
                                                            Card ID <span class="copy" data-clipboard-text="{{ @$cards[1]['card_id'] }}" data-clipboard-short></span>
                                                            <input disabled type="text" class="form-control text-primary {{ @$cards[1]['status'] == 'blocked' ? 'bg-danger text-white'  : '' }}" 
                                                                value="{{ @$cards[1]['card_id'] }}"   placeholder="">
                                                            <br>
                                                            Account ID <span class="copy" data-clipboard-text="{{ @$cards[1]['account_id'] }}" data-clipboard-short></span>
                                                            <input disabled type="text" class="form-control text-primary"
                                                                value="{{ @$cards[1]['account_id'] }}" >
                                                        </div>
                                                        <div class="form-group col-12 col-lg-6">
                                                            <label> 
                                                                <span class="color text-primary">
                                                                    {{ @$cards[1]['provider'] == 'fw' ? 'Flutterwave V2' : '' }}
                                                                    {{ @$cards[1]['provider'] == 'flutterwave' ? 'Flutterwave V1' : '' }}
                                                                    {{ @$cards[1]['provider'] == 'sudo' ? 'SUDO' : '' }} 
                                                                </span>
                                                                 on
                                                                {{ date('dS M Y, h:i A', @$cards[1]['issued']) }}
                                                                <br>
                                                                <span class="color" style="font-size: 17px;">
                                                                {{ @strtoupper($cards[1]['status']) }} 
                                                                </span>
                                                            </label>
                                                            <input disabled type="text" class="form-control" 
                                                                value="{{ @round($cards[1]['balance'], 2) }}$ - {{ @strtoupper($cards[1]['type']) }} "   placeholder="">
                                                        </div>
                                                        




                                                        <div class="form-group col-12 col-lg-6">
                                                            <label>
                                                                3rd Card {{ @$cards[2]['masked_pan'] }}
                                                                <span class="text-primary">{{ @strtoupper($cards[2]['type']) }}</span> 
                                                                <br>
                                                                <span class="color" style="font-size: 17px;">
                                                                {{ @strtoupper($cards[2]['cardholder']) }} 
                                                                </span>
                                                            </label>
                                                            <input disabled type="text" class="form-control {{ @$cards[2]['status'] == 'blocked' ? 'bg-danger text-white'  : '' }}" 
                                                                value="{{ @$cards[2]['card_id'] }}"   placeholder="">
                                                        </div>
                                                        <div class="form-group col-12 col-lg-6">
                                                            <label> 
                                                                <span class="color text-primary">
                                                                    {{ @$cards[2]['provider'] == 'fw' ? 'Flutterwave V2' : '' }}
                                                                    {{ @$cards[2]['provider'] == 'flutterwave' ? 'Flutterwave V1' : '' }}
                                                                    {{ @$cards[2]['provider'] == 'sudo' ? 'SUDO' : '' }} 
                                                                </span>
                                                                 on
                                                                {{ date('dS M Y, h:i A', @$cards[2]['issued']) }}
                                                                <br>
                                                                <span class="color" style="font-size: 17px;">
                                                                {{ @strtoupper($cards[2]['status']) }} 
                                                                </span>
                                                            </label>
                                                            <input disabled type="text" class="form-control" 
                                                                value="{{ @round($cards[2]['balance'], 2) }}$ - {{ @strtoupper($cards[2]['type']) }} "   placeholder="">
                                                        </div>




                                                        <div class="form-group col-12 col-lg-6">
                                                            <label>
                                                                4th Card {{ @$cards[3]['masked_pan'] }}
                                                                <span class="text-primary">{{ @strtoupper($cards[3]['type']) }}</span> 
                                                                <br>
                                                                <span class="color" style="font-size: 17px;">
                                                                {{ @strtoupper($cards[3]['cardholder']) }} 
                                                                </span>
                                                            </label>
                                                            <input disabled type="text" class="form-control {{ @$cards[3]['status'] == 'blocked' ? 'bg-danger text-white'  : '' }}" 
                                                                value="{{ @$cards[3]['card_id'] }}"   placeholder="">
                                                        </div>
                                                        <div class="form-group col-12 col-lg-6">
                                                            <label> 
                                                                <span class="color text-primary"> 
                                                                    {{ @$cards[3]['provider'] == 'fw' ? 'Flutterwave V2' : '' }}
                                                                    {{ @$cards[3]['provider'] == 'flutterwave' ? 'Flutterwave V1' : '' }}
                                                                    {{ @$cards[3]['provider'] == 'sudo' ? 'SUDO' : '' }} 
                                                                </span>
                                                                 on
                                                                {{ date('dS M Y, h:i A', @$cards[3]['issued']) }}
                                                                <br>
                                                                <span class="color" style="font-size: 17px;">
                                                                {{ @strtoupper($cards[3]['status']) }} 
                                                                </span>
                                                            </label>
                                                            <input disabled type="text" class="form-control" 
                                                                value="{{ @round($cards[3]['balance'], 2) }}$ - {{ @strtoupper($cards[3]['type']) }} "   placeholder="">
                                                        </div>


                                                        <div class="form-group col-12 col-lg-6">
                                                            <label>
                                                                5th Card {{ @$cards[4]['masked_pan'] }}
                                                                <span class="text-primary">{{ @strtoupper($cards[4]['type']) }}</span> 
                                                                <br>
                                                                <span class="color" style="font-size: 17px;">
                                                                {{ @strtoupper($cards[4]['cardholder']) }} 
                                                                </span>
                                                            </label>
                                                            <input disabled type="text" class="form-control {{ @$cards[4]['status'] == 'blocked' ? 'bg-danger text-white'  : '' }}" 
                                                                value="{{ @$cards[4]['card_id'] }}"   placeholder="">
                                                        </div>
                                                        <div class="form-group col-12 col-lg-6">
                                                            <label> 
                                                                <span class="color text-primary"> 
                                                                    {{ @$cards[3]['provider'] == 'fw' ? 'Flutterwave V2' : '' }}
                                                                    {{ @$cards[3]['provider'] == 'flutterwave' ? 'Flutterwave V1' : '' }}
                                                                    {{ @$cards[3]['provider'] == 'sudo' ? 'SUDO' : '' }} 
                                                                </span>
                                                                 on
                                                                {{ date('dS M Y, h:i A', @$cards[4]['issued']) }}
                                                                <br>
                                                                <span class="color" style="font-size: 17px;">
                                                                {{ @strtoupper($cards[4]['status']) }} 
                                                                </span>
                                                            </label>
                                                            <input disabled type="text" class="form-control" 
                                                                value="{{ @round($cards[4]['balance'], 2) }}$ - {{ @strtoupper($cards[4]['type']) }} "   placeholder="">
                                                        </div>


                                                         
                                                    </div> 
                                                </div>
                                                <div class="col-12 d-flex flex-sm-row flex-column justify-content-end mt-1">
                                                    <button type="submit" class="btn btn-primary glow mb-1 mb-sm-0 mr-0 mr-sm-1">{! $lang['change'] !}</button>
                                                    <!--<button type="reset" class="btn btn-outline-warning">Reset</button>-->
                                                </div> 
                                            </div>
                                        </form>
                                        <!-- users edit Info form ends -->
                                    </div>
                                    <div class="tab-pane 
                                        {% if ( isset($_GET['document']) ): %}
                                            active
                                        {% endif; %} 
                                    " id="social"   role="tabpanel">
                                        <!-- users edit socail form start --> 
                                        
                                        {% if (is_null($edit['cardholder_id'])): %}
                                            <a href="#cardholder" onclick="createCardholder()">
                                                <i class="feather icon-plus"></i>
                                                Create Cardholder
                                            </a>
                                        {% else: %}
                                            <p>
                                                Carddholder ID <span class="badge bg-success">
                                                    {{ $edit['cardholder_id'] }}
                                                </span>
                                            </p>
                                        {% endif; %}

                                        <br><br>  
                                        <div novalidate>
                                        <h4 class="mb-0">Know Your Customer (KYC)</h4>
                                                        <br>
                                            <div class="row">
                                                <div class="col-12 col-sm-12 "> 
                                                <div class="table-responsive border rounded px-1 ">
                                                        <table class="table table-borderless ignore no-radius">
                                                            <thead>
                                                                <tr> 
                                                                    <th class="text-primary">{! $lang['phone_verified'] !} </th>
                                                                    <th class="text-primary">{! $lang['email_verified'] !}</th>
                                                                    <th class="text-primary">{! $lang['terms_agreed'] !}</th> 
                                                                    <th class="text-primary">KYC Completed</th>
                                                                </tr>
                                                            </thead>
                                                            <tbody>
                                                                <tr> 
                                                                    <td>
                                                                        <div class="custom-control custom-checkbox">
                                                                            <input type="checkbox" id="users-checkbox10" class="custom-control-input" 
                                                                            {{ $edit['phone_verified'] == 'yes' ? 'checked' : '' }} disabled>
                                                                            <label class="custom-control-label" for="users-checkbox10"></label>
                                                                        </div>
                                                                    </td> 
                                                                    <td>
                                                                        <div class="custom-control custom-checkbox">
                                                                            <input type="checkbox" id="users-checkbox11" class="custom-control-input" 
                                                                            {{ $edit['email_verified'] == 'yes' ? 'checked' : '' }} disabled>
                                                                            <label class="custom-control-label" for="users-checkbox11"></label>
                                                                        </div>
                                                                    </td> 
                                                                    <td>
                                                                        <div class="custom-control custom-checkbox">
                                                                            <input type="checkbox" id="users-checkbox12" class="custom-control-input" 
                                                                            {{ $edit['terms_agreed'] == 'yes' ? 'checked' : '' }} disabled>
                                                                            <label class="custom-control-label" for="users-checkbox12"></label>
                                                                        </div>
                                                                    </td> 
                                                                    <td>
                                                                        <div class="custom-control custom-checkbox">
                                                                            <input type="checkbox" id="users-checkbox13" class="custom-control-input" 
                                                                            {{ $edit['kyc_verified'] == 'yes' ? 'checked' : '' }} disabled>
                                                                            <label class="custom-control-label" for="users-checkbox13"></label>
                                                                        </div>
                                                                    </td>
                                                                </tr>  
                                                            </tbody>
                                                        </table>
                                                    </div>

                                                   <div class="card">
                                                        <div class="card-header">
                                                            <h5 class="mb-0">{{ explode(' ', $edit['name'])[0] }} 's {! $lang['uploaded_documents'] !}</h5>
                                                        </div> 
                                                        <div class="card-content">
                                                            <div class="table-responsive mt-1">
                                                                <table class="table table-hover-animation mb-0 ignore">
                                                                    <thead>
                                                                        <tr><abcd@1234 class=""></abcd@1234>
                                                                            <th>{! $lang['id'] !}</th>
                                                                            <th>{! $lang['status'] !}</th> 
                                                                            <th>{! $lang['upload_date'] !}</th>
                                                                            <th>{! $lang['view'] !}</th>
                                                                            <th>{! $lang['comment'] !}</th>
                                                                            <th>{! $lang['action'] !}</th>
                                                                        </tr>
                                                                    </thead>
                                                                    <tbody>   
                                                                    { foreach $docs as $t }
                                                                    <tr>
                                                                            <td>#{{ $t['id'] }}</td>
                                                                            <td><i class="fa fa-circle font-small-3 mr-50 
                                                                                {{ $t['status'] == 'pending' ? 'text-warning' : '' }}
                                                                                {{ $t['status'] == 'approved' ? 'text-success' : '' }}
                                                                                {{ $t['status'] == 'declined' ? 'text-danger' : '' }}"></i>
                                                                                {{ strtoupper($t['status']) }}
                                                                            </td> 
                                                                            <td> {{ date('D dS M Y, h:i A', $t['upload_date']) }} </td>
                                                                            <td class="p-1">
                                                                                <a onclick="displayIdCard(`https://{{ $t['file_url'] }}`)" data-target="_blank">
                                                                                    <i class="feather icon-eye cursor-pointer"></i>
                                                                                </a>
                                                                                &nbsp;&nbsp;&nbsp;&nbsp;
                                                                                <a href="https://{{ $t['file_url'] }}" target="_blank">
                                                                                    <i class="feather icon-link cursor-pointer"></i>
                                                                                </a>
                                                                            </td>
                                                                            <td>
                                                                                {{ $t['reason'] }}
                                                                            </td>
                                                                            <td>
                                                                                <a data-url="https://{{ $t['file_url'] }}"  
                                                                                    data-userid="{{ $t['user_id'] }}"
                                                                                    data-document="{{ $t['id'] }}" 
                                                                                    class="{{ $t['status'] == 'pending' ? 'treat' : 'disabled' }}"
                                                                                    {{ $t['status'] == 'pending' ? '' : 'disabled' }}
                                                                                    >
                                                                                    {{ $t['status'] == 'pending' ? $lang2['treat_now'] : $lang2['treated'] }}
                                                                                </a>
                                                                            </td>
                                                                        </tr>
                                                                    { foreach }
                                                                    
                                                                    </tbody>
                                                                </table>
                                                            </div>
                                                        </div>
                                                   </div>
                                                     
                                                    <fieldset>
                                                        <form action="/editu" method="post">
                                                            <input type="hidden" name="editKYC" value="true">
                                                            <input type="hidden" name="user_id" value="{{ $edit['id'] }}">
                                                            <div class="row">
                                                                <div class="col-sm-12 col-md-12 col-lg-4 col-xl-3">
                                                                    <label class="text-primary">Occupation</label> 
                                                                    <div class="input-group mb-75">
                                                                        <div class="input-group-prepend">
                                                                            <span class="input-group-text feather icon-briefcase bg-primary text-white"></span>
                                                                        </div>
                                                                        <input readonly type="text" class="form-control" value="{{ is_null($edit['occup']) ? 'NOT SET' : strtoupper($edit['occup']) }}">
                                                                    </div>
                                                                </div>
                                                                <div class="col-sm-12 col-md-12 col-lg-4 col-xl-3">
                                                                    <label class="text-primary">Occupation Category</label> 
                                                                    <div class="input-group mb-75">
                                                                        <div class="input-group-prepend">
                                                                            <span class="input-group-text feather icon-layers bg-primary text-white"></span>
                                                                        </div>
                                                                        <input readonly type="text" class="form-control" 
                                                                        value="{{ $employment }}">
                                                                    </div>
                                                                </div>
                                                                <div class="col-sm-12 col-md-12 col-lg-4 col-xl-3">
                                                                    <label class="text-primary">Income Level (Monthly)</label> 
                                                                    <div class="input-group mb-75">
                                                                        <div class="input-group-prepend">
                                                                            <span class="input-group-text feather icon-dollar-sign bg-primary text-white"></span>
                                                                        </div>
                                                                        <input readonly type="text" class="form-control" value="{{ is_null($edit['occup_income']) ? 'NOT SET' : $edit['income_level'] }}">
                                                                    </div>
                                                                </div>
                                                                <div class="col-sm-12 col-md-12 col-lg-4 col-xl-3">
                                                                    <label class="text-primary">Tax ID</label> 
                                                                    <div class="input-group mb-75">
                                                                        <div class="input-group-prepend">
                                                                            <span class="input-group-text feather icon-printer bg-primary text-white"></span>
                                                                        </div>
                                                                        <input name="tax_id" type="text" class="form-control text-primary" value="{{ is_null($edit['tax_id']) ? 'NOT SET' : $edit['tax_id'] }}">
                                                                    </div>
                                                                </div>
                                                                <div class="col-sm-12 col-md-12 col-lg-4 col-xl-3">
                                                                    <label class="text-primary">Home Address</label> 
                                                                    <div class="input-group mb-75">
                                                                        <div class="input-group-prepend">
                                                                            <span class="input-group-text feather icon-map-pin bg-primary text-white"></span>
                                                                        </div>
                                                                        <input readonly type="text" class="form-control" value="{{  $edit['address'] }}, {{ $edit['city'] }}, {{  $edit['country_code'] }}">
                                                                    </div>
                                                                </div>
                                                                <div class="col-sm-12 col-md-12 col-lg-4 col-xl-3">
                                                                    <label class="text-primary">ID EXPIRATION: <strong style="text-transform: uppercase;">{{ $edit['id_expires'] == 0 ? 'NOT SET' : date('D, d M Y', $edit['id_expires']) }}</strong> </label> 
                                                                    <div class="form-check" style="margin-top:5px;">
                                                                        <label for="change_expiry" class="form-check-label">
                                                                            <input type="checkbox" class="form-check-input" name="change_expiry" value="true" id="change_expiry"
                                                                            style="margin-top:2px!important;">
                                                                            Change Expiry Date?
                                                                        </label>
                                                                    </div>
                                                                    <div class="input-group mb-75">
                                                                        <div class="input-group-prepend">
                                                                            <span class="input-group-text feather icon-calendar bg-primary text-white"></span>
                                                                        </div>
                                                                        <input type="date" name="id_expires" class="form-control {{ $edit['id_expires'] > 0 && $edit['id_expires'] < time() ? 'bg-danger text-white' : '' }}" dplaceholder="Set Expiry Date">
                                                                    </div>
                                                                </div>
                                                                <div class="col-sm-12 col-md-12 col-lg-4 col-xl-3">
                                                                    <label class="text-primary">Noupia Points</label> 
                                                                    <div class="input-group mb-75">
                                                                        <div class="input-group-prepend">
                                                                            <span class="input-group-text feather icon-plus-circle bg-primary text-white"></span>
                                                                        </div>
                                                                        <input readonly type="text" class="form-control {{ $edit['score'] >= 1000 ? 'text-success' : 'text-danger' }}" value="{{ $edit['score'] }}">
                                                                    </div>
                                                                </div>
                                                                <div class="col-sm-12 col-md-12 col-lg-4 col-xl-3">
                                                                    <label class="text-primary">Account Age</label> 
                                                                    <div class="input-group mb-75">
                                                                        <div class="input-group-prepend">
                                                                            <span class="input-group-text feather icon-clock bg-primary text-white"></span>
                                                                        </div>
                                                                        <input readonly type="text" class="form-control" value="{{ round( (time() - $edit['date_created'] ) / 2592000) }} Months">
                                                                    </div>
                                                                </div>
                                                                <div class="col-sm-12 col-md-12 col-lg-4 col-xl-3">
                                                                    <label class="text-primary">ID Card Number</label> 
                                                                    <div class="input-group mb-75">
                                                                        <div class="input-group-prepend">
                                                                            <span class="input-group-text feather icon-file-text bg-primary text-white"></span>
                                                                        </div>
                                                                        <input name="id_no" type="text" class="form-control text-primary" value="{{ is_null($edit['id_no']) ? 'NOT SET' : $edit['id_no'] }}">
                                                                    </div>
                                                                </div>
                                                                <div class="col-sm-12 col-md-12 col-lg-4 col-xl-3">
                                                                    <label class="text-primary">Transaction Volume</label> 
                                                                    <div class="input-group mb-75">
                                                                        <div class="input-group-prepend">
                                                                            <span class="input-group-text feather icon-activity bg-primary text-white"></span>
                                                                        </div>
                                                                        <input type="text" class="form-control text-success" readonly value="{{ $edit['t_volume'] > 0 ? '+' : '' }}{{ number_format($edit['t_volume']) }} CFA">
                                                                    </div>
                                                                </div>
                                                                <div class="col-12">
                                                                    <br>
                                                                    <label class="text-primary">
                                                                        Reason for using Noupia
                                                                        <span class="copy" data-clipboard-text="{{ is_null($edit['use_of_noupia']) ? 'NOT SET' : $edit['use_of_noupia'] }}" data-clipboard-short></span>
                                                                    </label>
                                                                    <div class="input-group">
                                                                        <textarea class="form-control" readonly style="height:90px;font-size:16px;border-left:5px solid #039be5!important;">{{ is_null($edit['use_of_noupia']) ? 'NOT SET' : $edit['use_of_noupia'] }}</textarea>
                                                                    </div>
                                                                </div>
                                                                <div class="col-12">
                                                                    <div class="form-group justify-content-end mt-1">
                                                                        <button type="submit" class="btn btn-primary glow mb-1 mb-sm-0 mr-0 mr-sm-1">
                                                                            <i class="feather icon-save"></i> Save Changes
                                                                        </button> 
                                                                    </div>
                                                                </div>
                                                            </div>
                                                        </form>
                                                    </fieldset>
                                                </div>
                                                <!--<div class="col-12 col-sm-6">
                                                    <label>Github</label>
                                                    <div class="input-group mb-75">
                                                        <div class="input-group-prepend">
                                                            <span class="input-group-text feather icon-github" id="basic-addon9"></span>
                                                        </div>
                                                        <input type="text" class="form-control" value="https://www.github.com/madop818" placeholder="https://www.github.com/" aria-describedby="basic-addon9">
                                                    </div>
                                                    <label>Codepen</label>
                                                    <div class="input-group mb-75">
                                                        <div class="input-group-prepend">
                                                            <span class="input-group-text feather icon-codepen" id="basic-addon12"></span>
                                                        </div>
                                                        <input type="text" class="form-control" value="https://www.codepen.com/adoptism243" placeholder="https://www.codepen.com/" aria-describedby="basic-addon12">
                                                    </div>
                                                    <label>Slack</label>
                                                    <div class="input-group mb-75">
                                                        <div class="input-group-prepend">
                                                            <span class="input-group-text feather icon-slack" id="basic-addon11"></span>
                                                        </div>
                                                        <input type="text" class="form-control" value="@gilopay" placeholder="https://www.slack.com/" aria-describedby="basic-addon11">
                                                    </div>
                                                </div> -->
                                               <!-- <div class="col-12 d-flex flex-sm-row flex-column justify-content-end mt-1">
                                                    <button type="submit" class="btn btn-primary glow mb-1 mb-sm-0 mr-0 mr-sm-1">Save
                                                        Changes</button>
                                                    <button type="reset" class="btn btn-outline-warning">Reset</button>
                                                </div> -->
                                            </div>
                                        </div>
                                        <!-- users edit socail form ends -->
                                    </div>
                                    <div class="tab-pane" id="transactions_"   role="tabpanel">
                                        <!-- users edit socail form start -->
                                        <form novalidate>
                                            <div class="row">
                                                <div class="col-12 col-sm-12 ">
 

                                                   <div class="card">
                                <div class="card-header">
                                    <h4 class="mb-0">{{ explode(' ', $edit['name'])[0] }} 's {! $lang['transactions'] !}</h4>
                                </div> 
                                <div class="card-content">
                                    <div class="table-responsive mt-1">
                                        <table class="table table-hover-animation mb-0">
                                            <thead>
                                                <tr>
                                                    <th>SN</th>
                                                    <th style="max-width: 80px!important;">Transaction ID</th>
                                                    <th>{! $lang['status'] !}</th>
                                                    <th style="min-width: 130px;">{! $lang['date'] !}</th>
                                                    <th>{! $lang['type'] !}</th>
                                                    <th>{! $lang['amount'] !}</th>
                                                    <th>{! $lang['sender'] !}</th>
                                                    <th>{! $lang['receiver'] !}</th>
                                                    <th>{! $lang['fees'] !}</th>
                                                    <th>{! $lang['description'] !}</th>
                                                    <th>{! $lang['reference'] !}</th>
                                                </tr>
                                            </thead>
                                            <tbody>
                                               { foreach $trans as $t }
                                               <tr>
                                                    <td>#{{ $t['id'] }}</td>
                                                    <td style="max-width: 100px!important;">
                                                        <span class="copy" data-clipboard-text="{{ $t['trans_id'] }}" data-clipboard-short></span>
                                                        <a href="/dashboard?trans_id={{ $t['trans_id'] }}" target="_blank" class="wrap-text">
                                                            {{ $t['trans_id'] }}
                                                        </a> 
                                                    </td>
                                                    <td><i class="fa fa-circle font-small-3 mr-50 
                                                        {{ $t['status'] == 'pending' ? 'text-warning' : '' }}
                                                        {{ $t['status'] == 'success' ? 'text-success' : '' }}
                                                        {{ $t['status'] == 'failed' ? 'text-danger' : '' }}
                                                        {{ $t['status'] == 'cancelled' ? 'text-danger' : '' }}
                                                     "></i>
                                                       {{ strtoupper($t['status']) }}
                                                    </td> 
                                                    <td > {{ date('D dS M Y, h:i A', $t['date_created']) }} </td>
                                                    <td class="p-1">
                                                        {{ strtoupper( $t['type']) }}
                                                    </td>
                                                    <td>
                                                        {{ $t['amount'] }} {{ strtoupper($t['currency']) }}
                                                    </td> 
                                                    <td>
                                                        <span class="copy text-primary" data-clipboard-text="{{ $t['sender']['name'] }}" data-clipboard-short></span>
                                                        {{ $t['sender']['name'] }} 
                                                    </td>
                                                    <td>
                                                        <span class="copy text-primary" data-clipboard-text="{{ $t['receiver']['name'] }}" data-clipboard-short></span>
                                                        {{ $t['receiver']['name'] }}
                                                    </td>
                                                    <td>
                                                        {{ $t['fee'] }} {{ strtoupper($t['currency']) }}
                                                    </td>
                                                    <td style="max-width:250px!important;">
                                                        {{ $t['description'] }} 
                                                    </td>
                                                    <td>
                                                        {{ substr($t['reference'], 0, 100) }} 
                                                    </td>
                                                </tr>       
                                               { foreach }
                                               
                                            </tbody>
                                        </table>
                                    </div>
                                </div>
                            </div>
                                                 
                                                </div> 
                                            </div>
                                        </form>
                                        <!-- users edit socail form ends -->
                                    </div>
                                    <div class="tab-pane" id="history" aria-labelledby="history-tab" role="tabpanel">
                                        <!-- users edit socail form start -->
                                        <form novalidate>
                                            <div class="row">
                                                <div class="col-12 col-sm-12 "> 

                                                   <div class="card">
                                                <div class="card-header">
                                                    <h4 class="mb-0">{{ explode(' ', $edit['name'])[0] }} 's {! $lang['balance_history'] !}</h4>
                                                </div>
                                
                                                    <div class="card-content">
                                                        <div class="table-responsive mt-1">
                                                            <table class="table table-hover-animation mb-0">
                                                                <thead>
                                                                    <tr>
                                                                        <th>{! $lang['id'] !}</th>
                                                                        <th>{! $lang['change'] !}</th> 
                                                                        <th>{! $lang['reason'] !}</th> 
                                                                        <th>{! $lang['before'] !}</th>
                                                                        <th>{! $lang['after'] !}</th>
                                                                        <th>{! $lang['fees'] !}</th>
                                                                        <th>{! $lang['date'] !}</th>
                                                                    </tr>
                                                                </thead>
                                                                <tbody>   
                                                                { foreach $history as $t }
                                                                    
                                                                <tr>
                                                                        <td>#{{ $t['id'] }}</td>
                                                                        <td class="{{ $t['_new'] - $t['previous'] > 0 ? 'text-success' : 'text-danger' }}"> 
                                                                            {{ number_format( $t['_new'] - $t['previous'] ) }} CFA 

                                                                        </td>
                                                                        <td><i class="fa fa-circle font-small-3 mr-50 text-success "></i>
                                                                        {{ strtoupper($t['reason']) }}
                                                                        </td> 
                                                                        <td> {{ number_format($t['previous']) }} CFA </td>
                                                                        <td class="p-1">
                                                                            {{ number_format($t['_new']) }} CFA
                                                                        </td> 
                                                                        <td>
                                                                            {{ number_format($t['fee']) }} CFA
                                                                        </td>
                                                                        <td>
                                                                            {{ date('D dS M Y, h:i A', $t['date_created']) }}
                                                                        </td>
                                                                    </tr>                                              
                                                                
                                                                { foreach }
                                                                
                                                                </tbody>
                                                            </table>
                                                        </div>
                                                    </div>
                                                </div>
                                                 
                                                </div> 
                                            </div>
                                        </form>
                                        <!-- users edit socail form ends -->
                                    </div>
                                    <div class="tab-pane" id="activities" aria-labelledby="history-activities" role="tabpanel">
                                        <!-- users edit socail form start -->
                                        <form novalidate>
                                            <div class="row">
                                                <div class="col-12 col-sm-12 "> 

                                                   <div class="card">
                                                <div class="card-header">
                                                    <h4 class="mb-0">{{ explode(' ', $edit['name'])[0] }} 's {! $lang['activity'] !}</h4>
                                                </div>
                                
                                                    <div class="card-content">
                                                        <div class="table-responsive mt-1">
                                                            <table class="table table-hover-animation mb-0">
                                                                <thead>
                                                                    <tr>
                                                                        <th>{! $lang['id'] !}</th>
                                                                        <th>{! $lang['page'] !}</th> 
                                                                        <th>{! $lang['description'] !}</th> 
                                                                        <th>{! $lang['device'] !}</th>
                                                                        <th>{! $lang['type'] !}</th>
                                                                        <th>{! $lang['date'] !}</th>
                                                                        <th>{! $lang['ip'] !} Address</th> 
                                                                        <th>{! $lang['coordinates'] !}</th>
                                                                    </tr>
                                                                </thead>
                                                                <tbody>   
                                                                { foreach $activities as $t }
                                                                    
                                                                    <tr>
                                                                        <td>#{{ $t['id'] }} </td>
                                                                        <td> {{ strtoupper($t['page']) }}  </td>
                                                                        <td style="max-width:250px!important;">
                                                                            <i class="fa fa-circle font-small-3 mr-50 text-success "></i>
                                                                            {{ ($t['description']) }}
                                                                        </td> 
                                                                        <td> {{ $t['device'] }} </td>
                                                                        <td class="p-1">
                                                                            {{  $t['type'] }}
                                                                        </td> 
                                                                        <td>
                                                                            {{ date('D dS M Y, h:i A', $t['date_created']) }}
                                                                        </td>
                                                                        <td>
                                                                            <a href="https://ipinfo.io/{{ $t['ip_address'] }}" target="_blank">
                                                                                {{ $t['ip_address'] }}
                                                                            </a> 
                                                                        </td>
                                                                        <td>
                                                                            {{ $t['coords'] }}
                                                                        </td>
                                                                    </tr>                                              
                                                                
                                                                { foreach }
                                                                
                                                                </tbody>
                                                            </table>
                                                        </div>
                                                    </div>
                                                </div>
                                                 
                                                </div> 
                                            </div>
                                        </form>
                                        <!-- users edit socail form ends -->
                                    </div>
                                    <div class="tab-pane" id="behaviours"   role="tabpanel">
                                        <!-- users edit socail form start -->
                                        <form novalidate>
                                            <div class="row">
                                                <div class="col-12 col-sm-12 "> 

                                                   <div class="card">
                                                <div class="card-header">
                                                    <h4 class="mb-0">{{ explode(' ', $edit['name'])[0] }} 's BEHAVIOUR</h4>
                                                </div>
                                                    <div class="card-content">
                                                        <div class="table-responsive mt-1">
                                                            <table class="table table-hover-animation mb-0">
                                                                <thead>
                                                                    <tr>
                                                                        <th> ID </th>
                                                                        <th> Comment </th> 
                                                                        <th>Points</th>  
                                                                        <th>{! $lang['type'] !}</th>
                                                                        <th>{! $lang['date'] !}</th> 
                                                                        <th>TIME</th>
                                                                    </tr>
                                                                </thead>
                                                                <tbody>   
                                                                { foreach $behaviours as $b }
                                                                    
                                                                    <tr>
                                                                        <td>#{{ $b['id'] }} </td> 
                                                                        <td style="max-width:250px!important;">
                                                                            <i class="fa fa-circle font-small-3 mr-50 text-succes {{  $b['point'] > 0 ? 'text-success' : 'text-danger'  }}"></i>
                                                                            {{ ($b['comment']) }}
                                                                        </td>
                                                                        <td class="p-1 {{  $b['point'] > 0 ? 'text-success' : 'text-danger'  }}">
                                                                          {{  $b['point'] > 0 ? '+' : ''  }}{{  $b['point'] }}
                                                                        </td>
                                                                        <td class="p-1 {{  $b['point'] > 0 ? 'text-success' : 'text-danger'  }}">
                                                                            {{  $b['point'] > 0 ? 'POSITIVE' : 'NEGATIVE'  }}
                                                                        </td> 
                                                                        <td>
                                                                            {{ date('D dS M Y', $b['date_created']) }}
                                                                        </td>  
                                                                        <td>
                                                                            {{ date('h:i A', $b['date_created']) }}
                                                                        </td>
                                                                    </tr>                                              
                                                                
                                                                { foreach }
                                                                
                                                                </tbody>
                                                            </table>
                                                        </div>
                                                    </div>
                                                </div>
                                                 
                                                </div> 
                                            </div>
                                        </form>
                                        <!-- users edit socail form ends -->
                                    </div>
                                    <div class="tab-pane" id="bankaccounts"   role="tabpanel">
                                        <div class="row">
                                            <div class="col-12 col-sm-12 "> 

                                                <div class="card">
                                            <div class="card-header">
                                                <h4 class="mb-0">{{ explode(' ', $edit['name'])[0] }} 's Virtual Accounts</h4>
                                            </div>
                                                <div class="card-content">
                                                    <div class="table-responsive mt-1">
                                                        <table class="table table-hover-animation mb-0">
                                                            <thead>
                                                                <tr>
                                                                    <th>ID</th>
                                                                    <th>Status</th>
                                                                    <th style="width:200px!important;white-space: initial!important;">Purpose</th> 
                                                                    <th>Activity</th>
                                                                    <th>Zone</th> 
                                                                    <th>Range</th>  
                                                                    <th>Date Created</th>  
                                                                </tr>
                                                            </thead>
                                                            <tbody>   
                                                            { foreach $banks as $b }
                                                                
                                                                <tr>
                                                                    <td>{{ $b['id'] }} </td>
                                                                    <td class="
                                                                        {{ $b['status'] == 'active' ? 'text-success' : '' }}
                                                                        {{ $b['status'] == 'pending' ? 'text-warning' : '' }}
                                                                        {{ $b['status'] == 'suspended' ? 'text-danger' : '' }}">
                                                                            <span id="bankAccount{{ $b['id'] }}">
                                                                                {{ strtoupper($b['status']) }}
                                                                            </span>
                                                                            <select name="status" class="form-control"
                                                                                data-ajax-post="/ajax" 
                                                                                data-ajax-trigger="change"
                                                                                data-ajax-include='{{ json_encode([ "id" => $b["id"], "operation" => "updateBankAccount" ]) }}'
                                                                                data-ajax-result="#bankAccount{{ $b['id'] }}">
                                                                                <option disabled value="" selected>Update Status</option>
                                                                                <option value="active" {{ $b['status'] == 'active' ? 'disabledd' : '' }}>Active</option>
                                                                                <option value="pending" {{ $b['status'] == 'pending' ? 'disabledd' : '' }}>Pending</option>
                                                                                <option value="suspended" {{ $b['status'] == 'suspended' ? 'disabledd' : '' }}>Suspended</option>
                                                                            </select>
                                                                        </div>
                                                                    </td>
                                                                    <td style="width:200px!important;white-space: initial!important;">
                                                                        {{ ($b['purpose']) }}
                                                                    </td>
                                                                    <td> {{ $b['occupation'] }} </td>
                                                                    <td class="p-1">
                                                                        <span class="badge badge-primary">{{ strtoupper($b['zone']) }}</span>
                                                                    </td>
                                                                    <td>
                                                                        {{ $b['range_'] }} {{ $b['frequency'] }}
                                                                    </td> 
                                                                    <td>
                                                                        {{ date('D dS M Y', $b['date_created']) }} -
                                                                        {{ date('h:i A', $b['date_created']) }}
                                                                    </td>  
                                                                </tr>                                              
                                                            
                                                            { foreach }
                                                            
                                                            </tbody>
                                                        </table>
                                                    </div>
                                                </div>
                                            </div>
                                                
                                            </div> 
                                        </div>
                                    </div>
                                    <div class="tab-pane 
                                        {% if ( isset($_GET['logs']) ): %}
                                            active
                                        {% endif; %}
                                    " id="errors"   role="tabpanel">
                                        <!-- users edit socail form start -->
                                        <form novalidate>
                                            <div class="row">
                                                <div class="col-12 col-sm-12 "> 

                                                   <div class="card">
                                                <div class="card-header">
                                                    <h4 class="mb-0">System Logs</h4>
                                                </div>
                                                    <div class="card-content">
                                                        <div class="table-responsive mt-1">
                                                            <table class="table table-hover-animation mb-0">
                                                                <thead>
                                                                    <tr>
                                                                        <th> ID </th>
                                                                        <th> Type </th>
                                                                        <th> Sent by</th> 
                                                                        <th> Description </th>   
                                                                        <th>{! $lang['date'] !}</th> 
                                                                        <th>TIME</th>
                                                                    </tr>
                                                                </thead>
                                                                <tbody>   
                                                                {% if (isset($_GET['logs'])): %}
                                                                    { foreach @$logs as $b } 
                                                                        <tr>
                                                                            <td>#{{ $b['id'] }} </td> 
                                                                            <td>
                                                                                {{ strtoupper($b['description']) }}
                                                                            </td>
                                                                            <td class="p-1 text-success">
                                                                                {{ strtoupper($b['sent_by']) }}
                                                                            </td> 
                                                                            <td style="max-width:250px!important;">
                                                                                <i class="fa fa-circle font-small-3 mr-50 text-danger"></i>
                                                                                {{ ($b['message']) }}
                                                                            </td>
                                                                            <td>
                                                                                {{ date('D dS M Y', $b['date_created']) }}
                                                                            </td>  
                                                                            <td>
                                                                                {{ date('h:i A', $b['date_created']) }}
                                                                            </td>
                                                                        </tr>
                                                                    { foreach }
                                                                {% endif; %}
                                                                </tbody>
                                                            </table>
                                                        </div>
                                                    </div>
                                                </div>
                                                 
                                                </div> 
                                            </div>
                                        </form>
                                        <!-- users edit socail form ends -->
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </section>
                <!-- users edit ends -->

            </div>
        </div>
        <br><br><br>
    </div>
    <!-- END: Content-->








    <!-- END: Content-->

    <div class="sidenav-overlay"></div>
    <div class="drag-target"></div>

    <!-- BEGIN: Footer-->
    @load('inc/footer.php')
    <!-- END: Footer-->

    <!-------- scripts -------->
    
    
    <!-- BEGIN: Vendor JS-->
    <script src="/public/vuexy/app-assets/vendors/js/vendors.min.js"></script>
    <!-- BEGIN Vendor JS-->

    <!-- BEGIN: Page Vendor JS-->
    <script src="/public/vuexy/app-assets/vendors/js/ui/jquery.sticky.js"></script>
    <script src="/public/vuexy/app-assets/vendors/js/forms/select/select2.full.min.js"></script>
    <script src="/public/vuexy/app-assets/vendors/js/forms/validation/jqBootstrapValidation.js"></script>
    <script src="/public/vuexy/app-assets/vendors/js/pickers/pickadate/picker.js"></script>
    <script src="/public/vuexy/app-assets/vendors/js/pickers/pickadate/picker.date.js"></script>
    <!-- END: Page Vendor JS-->

    <!-- BEGIN: Theme JS-->
    <script src="/public/vuexy/app-assets/js/core/app-menu.js"></script>
    <script src="/public/vuexy/app-assets/js/core/app.js"></script>
    <script src="/public/vuexy/app-assets/js/scripts/components.js"></script>
    <!-- END: Theme JS-->

    <!-- BEGIN: Page JS-->
    <script data-src="/public/vuexy/app-assets/js/scripts/pages/app-user.js"></script>
    <script src="/public/vuexy/app-assets/js/scripts/navs/navs.js"></script>
    <!-- END: Page JS-->
    <script>
         
        $('.treat').click(function(){
            
            let document = $(this).data('document')
            let fileurl = $(this).data('url')
            let type = 'ID ' //$(this).data('type')
            let userid = $(this).data('userid')
 
        
        Swal.fire({
            title: `<strong> ${type} <u> {{ $lang2['document'] }} </u></strong>`, 
            html :    ` {{  $lang2['treat2'] }} `
                
            , 
            imageUrl : fileurl,
            imageHeight : 300,
            showCloseButton: true,
            showCancelButton: true,
            showConfirmButton: true,
            focusConfirm: false,
            confirmButtonText:
            `<i class="fa fa-thumbs-up"></i>  <span data-trans-action="approve">{{ $lang2['approve'] }}</span> `,
            confirmButtonAriaLabel: 'Thumbs up, great!',
            cancelButtonText:
            `<i class="fa fa-thumbs-down"></i> <span data-trans-action="reject">{{ $lang2['reject'] }}</span>`,
            cancelButtonAriaLabel: 'Thumbs down'  
            
        })
        .then(function(res){
            
                if (res.value) {

                Swal.fire({
                title: '{{ $lang2['approve2'] }}',
                html: ` 
                    <p class="text-primary"> User's Language: {{ strtoupper($edit['language']) }}</p>
                    <p style="color:black;"> 
                        <a href="#front-" onclick="uploadText('front')">Front</a> |
                        <a href="#back-" onclick="uploadText('back')">Back</a> |
                        <a href="#selfie-" onclick="uploadText('selfie')">Selfie</a> |
                        <a href="#already-" onclick="uploadText('already')">Have already</a> |
                        <a href="#camera-" onclick="uploadText('camera')">Camera</a> |
                        <a href="#good-picture-" onclick="uploadText('good-picture')">Good pictures</a> |
                        <a href="#visible-selfie-" onclick="uploadText('visible-selfie')">Visible Selfie</a> |
                        <a href="#four-coner-" onclick="uploadText('four-coner')">4Coners</a> |
                         <a href="#extension-" onclick="uploadText('extension')">Extension</a> 
                    </p>
                    <textarea  placeholder="Type a comment (optional)" style="width:100%;height:150px;" class="swal-input swal-approve-reason document-upload-reply"></textarea> `,
                icon: 'warning',
                showCancelButton: true,
                confirmButtonColor: '#3085d6',
                cancelButtonColor: '#d33',
                confirmButtonText: '{{ $lang2['yes_approve'] }}'
                }).then(function(result){ 

                    let reason = $('body').find('.swal-approve-reason').val()
                    
                    if (result.value) { 
                            $.ajax({
                                type : 'POST',
                                url : `/api/post/documents/${document}/approved`,
                                data : { 
                                    reason : reason,
                                    role : '{{ $role }}'
                                },
                                complete : function(){  
                                    window.location = `/users?edit=${userid}&mssg={! $lang2['approve_success'] !}&document`
                                }
                        })
                    }
                })
            }
            else if (res.dismiss == 'cancel') {
            
                // function when cancel button is clicked
                Swal.fire({ 
                    title: '{{ $lang2['reject2'] }}', 
                    html: `
                     <p class="text-primary"> User's Language: {{ strtoupper($edit['language']) }}</p>
                     <p style="color:black;"> 
                        <a href="#front-" onclick="uploadText('front')">Front</a> |
                        <a href="#back-" onclick="uploadText('back')">Back</a> |
                        <a href="#selfie-" onclick="uploadText('selfie')">Selfie</a> | 
                        <a href="#already-" onclick="uploadText('already')">Have already</a> |
                        <a href="#camera-" onclick="uploadText('camera')">Camera</a> |
                        <a href="#good-picture-" onclick="uploadText('good-picture')">Good pictures</a> |
                        <a href="#visible-selfie-" onclick="uploadText('visible-selfie')">Visible Selfie</a> |
                        <a href="#four-coner-" onclick="uploadText('four-coner')">4Coners</a> |
                         <a href="#extension-" onclick="uploadText('extension')">Extension</a> 
                     </p>
                     <textarea placeholder="Type a comment (optional)" style="width:100%;height:150px;" 
                     class="swal-input swal-decline-reason document-upload-reply"></textarea>`,
                    icon: 'warning',
                    showCancelButton: true,
                    confirmButtonColor: '#3085d6',
                    cancelButtonColor: '#d33',
                    confirmButtonText: '{{ $lang2['reject4'] }}'

                }).then((result) => {

                    let reason = $('body').find('.swal-decline-reason').val()

                    if (result.value) { 
                        $.ajax({
                            type : 'POST',
                            url : `/api/post/documents/${document}/declined`,
                            data : {
                                reason : reason,
                                role : '{{ $role }}'
                            },
                            complete : function(){  
                                window.location = `/users?edit=${userid}&mssg={! $lang2['reject_success'] !}&document`
                            }
                        })
                    }
                })
            }
            
            else {
                // console.log(res)
            }
            
            
        }, function(dismiss){
            
            console.log(dismiss)
        })

        window.uploadText = function(type) {
             
            let types = {
                'en' : {
                    'front' : `Please, upload the front side of this ID.`,
                    'back' :  `Kindly upload the back side of your ID card.`,
                    'selfie' : `Kindly upload a selfie of you holding this ID card.`,
                    'already': `We have received this photo already.`,
                    'camera': `Please take the picture with your phone's camera before uploading from your phone's gallery.`,
                    'good-picture': `ID card is not clear and visible, Kindly make sure the ID card does not cover your face nor should your hand cover any information.`,
                    'visible-selfie': `Kindly upload a more appropriate and visible photo of yourself holding this ID card next to your face, ensuring that all information on the ID card is clearly visible.`,
                    'four-coner': `Please upload proper and visible pictures where all four corners of your ID and information on your ID are clearly visible.`,
                    'extension': `Kindly upload the back side of this ID card, which shows the extended expiration date.`,


                },

                'fr' : {
                    'front' : `Veuillez télécharger le recto de cette carte d'identité.`,
                    'back' :  `Veuillez télécharger le verso (derrière) de votre carte d'identité.`,
                    'selfie' : `Veuillez télécharger une photo selfie de vous tenant cette carte d'identité.`,
                    'already': `Nous avons déjà reçu et approuvé cette photo.`,
                    'camera': `Veuillez utiliser l'appareil photo de votre téléphone pour prendre la photo avant de la télécharger dans la galerie de votre téléphone.`,
                    'good-picture': ` La carte d'identité n'est pas claire et visible. Veuillez vous assurer que la carte d'identité ne couvre pas votre visage et que votre main ne couvre aucune information.`,
                    'visible-selfie': `Veuillez télécharger une photo plus appropriée et plus visible de vous tenant cette carte d'identité à côté de votre visage, en veillant à ce que toutes les informations figurant sur la carte d'identité soient clairement visibles.`,
                    'four-coner': `Veuillez télécharger des photos appropriées et visibles où les quatre bords de votre carte d'identité et les informations qu'elle contient sont clairement visibles.`,
                    'extension': `Veuillez télécharger le verso de votre carte d'identité, montrant la date d'expiration prolongée.`,
                },

                'es' : {
                    'front' : `Por favor, suba el anverso de este documento de identidad.`,
                    'back' :  `Por favor, suba el reverso de su documento de identidad.`,
                    'selfie' : `Por favor, suba un selfie de usted sosteniendo esta tarjeta de identificación.`,
                    'already' : `Ya hemos recibido y aprobado esta foto.`,
                    'camera': `Please take the picture with your phone's camera before uploading from your phone's gallery.
.`,
                    'good-picture': `Please make, Make sure the ID card is clear and visible. Make sure the ID card does not cover your face. Make sure your hand does not cover any information.
.`,
                    'visible-selfie': `Kindly upload a more appropriate and visible photo of yourself holding this ID card next to your face, ensuring that all information on the ID card is clearly visible.
.`,
                    'four-coner': `Please upload proper and visible pictures where all four corners of your ID and information on your ID are clearly visible.`,
                    'extension': `Kindly upload the back side of this ID card, which shows the extended expiration date.`,
                },
            }

            let lang = '{{ $edit["language"] }}'
            let text = types[lang][type]
            //console.log(types[lang][type])
            $('.document-upload-reply').val(text)
        }
    })
      
    </script>
    
    <script>
        $(function () {
            $('.data-resend-email-confirmation').click(function (e) {
                e.preventDefault()
                let code = $(this).attr('data-token')
                let email = $(this).attr('data-email')
                let language = $(this).attr('data-language')
                let account = $(this).attr('data-account')
                let name = $(this).attr('data-name')
                let id = $(this).attr('data-id')
                const send = {
                    resendEmailConfirmationCode : true,
                    email: email,
                    language: language,
                    code: code,
                    name : name,
                    account: account,
                }

                $.ajax({
                    type : 'POST',
                    url: '/editu',
                    data : send,
                    success: function (res) {
                        console.log(res)
                    },
                    complete : function (params) {
                        window.location = `/users?edit=${id}&msg=Email confirmation code was re-sent successfully.`
                    }
                }) 
            })
        })
    </script>
    <link rel="stylesheet" href="//cdn.datatables.net/1.13.1/css/jquery.dataTables.min.css">
    <script src="https://cdn.datatables.net/1.13.1/js/jquery.dataTables.min.js" ></script>
    <script type="text/javascript" language="javascript" src="https://code.jquery.com/jquery-3.3.1.js"></script>
    <script type="text/javascript" language="javascript" src="https://cdn.datatables.net/1.10.19/js/jquery.dataTables.min.js"></script>
    <script type="text/javascript" language="javascript" src="https://cdn.datatables.net/select/1.2.7/js/dataTables.select.min.js"></script>
    <script type="text/javascript" language="javascript" src=" https://cdn.datatables.net/buttons/1.5.4/js/dataTables.buttons.min.js"></script>
    <script type="text/javascript" language="javascript" src="https://cdnjs.cloudflare.com/ajax/libs/jszip/3.1.3/jszip.min.js"></script>
    <script type="text/javascript" language="javascript" src="https://cdnjs.cloudflare.com/ajax/libs/pdfmake/0.1.36/pdfmake.min.js"></script>
    <script type="text/javascript" language="javascript" src="https://cdnjs.cloudflare.com/ajax/libs/pdfmake/0.1.36/vfs_fonts.js"></script>
    <script type="text/javascript" language="javascript" src="https://cdn.datatables.net/buttons/1.5.4/js/buttons.html5.min.js"></script>
    <script type="text/javascript" language="javascript" src="https://cdn.datatables.net/buttons/1.5.4/js/buttons.print.min.js"></script>

    <script>
        $(function(){ 
            //$.noConflict() 
            $('table').not('.ignore').DataTable({
                pagingType: 'full_numbers',
                ordering:  false,
                lengthChange: true,
                pageLength: 50,
                dom: 'Bfrtip',
                buttons: [  // Tutorial at: https://stackoverflow.com/questions/53787926/export-buttons-datatable
                    {
                        extend: 'pdfHtml5',
                        orientation: 'landscape',
                        pageSize: 'A4'
                    },
                    'excel',
                    'print', 
                    //'csv',
                    //'copy'
                    
                ]
            })
            
            window.createCardholder = function(){
                /**
                 * https://docs.bridgecard.co/reference/api-reference/kyc-requirements-for-all-countries
                 */
                
                Swal.fire({ 
                    title: `<span class="text-primary">Create a Cardholder</span>`, 
                    html: ` 
                    <!--<center>
                        <i class="feather icon-dollar-sign text-primary" style="font-size:60px;"></i>
                    </center>--> 
                    <form novalidate action="/ch" method="post" style="overflow:hidden!important;">
                        <input type="hidden" name="user_id" value="{{ $edit['id'] }}"> 
                        <input type="hidden" name="city" value="{{ $edit['city'] }}">
                        <input type="hidden" name="address" value="{{ $edit['address'] }}"> 
                        <input type="hidden" name="postal_code" value="563"> 
                        <input type="hidden" name="email" value="{{ $edit['email'] }}"> 
                        <input type="hidden" name="house_number" value="001"> 
                        <input type="hidden" name="id_number" value="{{ $edit['id_no'] }}"> 
                        <input type="hidden" name="customer_id" value="{{ $edit['account_number'] }}"> 
                        <center>
                            <div class="aler text-primary">
                            for {{ $edit['name'] }} 
                            </div>
                            <br>
                            <div class="row">
                                <div class="form-group col-12" dstyle="min-width:350px!important;min-height:10px;">
                                    <div class="controls row">
                                    <div class="col-6">
                                        <label style="float:left!important;"><strong>First name</strong></label>
                                        <input type="text" class="form-control" name="fname" required value="{{ $edit['firstname'] }}">
                                    </div>
                                    <div class="col-6">
                                        <label style="float:left!important;"><strong>Last name</strong></label>
                                        <input type="text" class="form-control" name="lname" required value="{{ $edit['lastname'] }}">
                                    </div>
                                    </div>
                                    
                                <div class="row controls">
                                    <div class="col-6">
                                        <label style="float:left!important;"><strong>Phone Number</strong></label>
                                        <input type="text" class="form-control" name="phone" required value="{{ $edit['phone_code'] }}{{ $edit['phone'] }}">
                                    </div>
                                <div class="col-6"> 
                                    <label style="float:left!important;"><strong>Country</strong></label>
                                        <select class="form-control" name="country" required>
                                            <option value="" selected disabled>Please select</option>
                                            <option value="Cameroon">CAMEROON</option> 
                                            <option value="Benin Republic">BENIN REPUBLIC</option>
                                            <option value="Gabon">GABON</option>
                                            <option value="Burkina Faso">BURKINAFASO</option>
                                            <option value="Congo Brazzaville">CONGO BRAZZAVILLE</option>
                                            <option value="Congo">CONGO KINSHASA</option>
                                            <option value="Ivory coast">IVORY COAST</option>
                                            <option value="Mali">MALI</option>
                                            <option value="Senegal">SENAGAL</option>
                                            <option value="Uganda">UGANDA</option>
                                        </select>
                                    </div>
                                </div>
                                <div class="row controls">
                                    <div class="col-6"> 
                                        <select class="form-control" name="state" required>
                                            <option value="" selected disabled>State</option>
                                            <option value="Littoral">Littoral(CM,BJ)</option> 
                                            <option value="Southwest">Southwest(CM)</option>
                                            <option value="Estuaire">Estuaire(GB)</option>
                                            <option value="Nyanga">Nyanga(GB)</option>
                                            <option value="Abidjan">Abidjan (CI)</option>
                                            <option value="Brazzaville">Brazzaville (CG)</option>
                                            <option value="Kinshasa">Kinshasa (CD)</option>
                                        </select>
                                    </div>
                                    <br>
                                    <div class="col-6"> 
                                         <select class="form-control" name="id_type" required>
                                        <option value="" selected disabled>ID Type</option>
                                            <optgroup label="CAMEROON">
                                                <option value="CAMEROON_NATIONAL_ID">CAMEROON NATIONAL ID</option>
                                                <option value="CAMEROON_VOTER_ID">CAMEROON VOTER ID</option> 
                                                <option value="CAMEROON_PASSPORT">CAMEROON PASSPORT</option> 
                                                <option value="CAMEROON_DRIVERS_LICENSE">CAMEROON DRIVERS LICENSE</option>
                                            </optgroup>
                                            <optgroup label="BENIN">
                                                <option value="BENIN_REPUBLIC_NATIONAL_ID">BENIN REPUBLIC NATIONAL ID</option> 
                                                <option value="BENIN_REPUBLIC_PASSPORT">BENIN REPUBLIC PASSPORT</option>
                                                <option value="BENIN_REPUBLIC_DRIVERS_LICENSE">BENIN REPUBLIC DRIVERS LICENSE</option>
                                                <option value="BENIN_REPUBLIC_VOTER_ID">BENIN REPUBLIC VOTER ID</option>
                                                <option value="BENIN_REPUBLIC_RESIDENT_CARD">BENIN REPUBLIC RESIDENT CARD</option>
                                            </optgroup>
                                            <optgroup label="BURKINAFASO">
                                                <option value="BURKINAFASO_VOTER_ID">BURKINAFASO VOTER ID</option> 
                                                <option value="BURKINAFASO_PASSPORT">BURKINAFASO PASSPORT</option>
                                                <option value="BURKINAFASO_NATIONAL_ID">BURKINAFASO NATIONAL ID</option>
                                                <option value="BURKINAFASO_DRIVERS_LICENSE">BURKINAFASO DRIVERS LICENSE</option>
                                            </optgroup>
                                            <optgroup label="CONGO BRAZZAVILLE">
                                                <option value="CONGO_BRAZZAVILLE_DRIVERS_LICENSE">CONGO BRAZZAVILLE DRIVERS LICENSE</option> 
                                                <option value="CONGO_BRAZZAVILLE_PASSPORT">CONGO BRAZZAVILLE PASSPORT </option>
                                                <option value="CONGO_BRAZZAVILLE_NATIONAL_ID">CONGO BRAZZAVILLE NATIONAL ID</option>
                                            </optgroup>
                                            <optgroup label="CONGO KINSHASHA">
                                                <option value="CONGO_DRIVERS_LICENSE">CONGO DRIVERS LICENSE</option> 
                                                <option value="CONGO_PASSPORT">CONGO PASSPORT </option>
                                                <option value="CONGO_NATIONAL_ID">CONGO NATIONAL ID</option>
                                            </optgroup>
                                            <optgroup label="GABON">
                                                <option value="GABON_NATIONAL_ID">GABON NATIONAL ID</option> 
                                                <option value="GABON_PASSPORT">GABON PASSPORT</option>
                                                <option value="GABON_RESIDENT_CARD">GABON RESIDENT CARD</option>
                                                <option value="GABON_HEALTH_INSURANCE_ID">GABON HEALTH INSURANCE ID</option>
                                            </optgroup>
                                            <optgroup label="IVORY COAST">
                                                <option value="IVORYCOAST_NATIONAL_ID">IVORYCOAST NATIONAL ID</option> 
                                                <option value="IVORYCOAST_DRIVERS_LICENSE">IVORYCOAST DRIVERS LICENSE</option>
                                                <option value="IVORYCOAST_PASSPORT">IVORYCOAST PASSPORT</option>
                                                <option value="IVORYCOAST_RESIDENT_CARD">IVORYCOAST RESIDENT CARD</option>
                                                <option value="IVORYCOAST_HEALTH_INSURANCE_ID">IVORYCOAST HEALTH INSURANCE ID</option>
                                            </optgroup>
                                            <optgroup label="MALI">
                                                <option value="MALI_NATIONAL_ID">MALI NATIONAL ID</option> 
                                                <option value="MALI_PASSPORT">MALI PASSPORT</option>
                                            </optgroup>
                                            <optgroup label="SENEGAL">
                                                <option value="SENEGAL_NATIONAL_ID">SENEGAL NATIONAL ID</option> 
                                                <option value="SENEGAL_ECOWAS_ID">SENEGAL ECOWAS ID</option>
                                            </optgroup>

                                        </select>
                                    </div>
                                    <br>
                                 </div>
                                </br>

                                  <p ><strong>Select ID Front Image</strong></p>
                                    <div class="row controls bg-primary">
                                    { foreach $docs as $d }
                                        <div class="col-4">
                                            <label>
                                                <input type="radio" name="id_front" value="https://{{ $d['file_url'] }}" id="id_front" required>
                                                <img src="https://{{ $d['file_url'] }}" height="60">
                                            </label>
                                        </div>
                                    { foreach }    
                                    </div>
                                    </br>

                                    <p><strong>Select ID Back Image</strong></p>
                                    <div class="row controls bg-primary">
                                    { foreach $docs as $d }
                                        <div class="col-4">
                                            <label>
                                                <input type="radio" name="id_back" value="https://{{ $d['file_url'] }}" required>
                                                <img src="https://{{ $d['file_url'] }}" height="60">
                                            </label>
                                        </div>
                                    { foreach }    
                                    </div>
                                    </br>

                                    <p><strong>Select ID Selfie </strong></p>
                                    <div class="row controls bg-primary">
                                    { foreach $docs as $d } 
                                        <div class="col-4">
                                            <label>
                                                <input type="radio" name="id_selfie" value="https://{{ $d['file_url'] }}" required>
                                                <img src="https://{{ $d['file_url'] }}" height="60">
                                            </label>
                                        </div>
                                    { foreach }    
                                    </div>
                                </div>
                            </div>
                        </center>
                        <button type="submit" class="btn btn-primary btn-block glow mb-1 mb-sm-0 mr-0 mr-sm-1 waves-effect waves-light">
                            Create
                        </button>
                    </form>
                    
                    `,
                    showConfirmButton: false,
                    showCloseButton: true,
                    allowOutsideClick: false,
                    allowEscapeKey: false,
                })
            }
        })
    </script> 
</body>
<!-- END: Body-->

</html>
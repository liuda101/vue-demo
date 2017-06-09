<template>
<i :class="classes"></i>
</template>

<script>
export default {
  name: 'Icon',
  props: {
    type: String
  },
  computed: {
    classes: function () {
      return ['iui-icon', 'iui-icon-' + this.type].join(' ')
    }
  }
}
</script>

<style>
@font-face {
  font-family: "icon-bass";
  src: url('./font/icon-bass.eot');
  src: url('./font/icon-bass.eot?#iefix') format('eot'),
    url('./font/icon-bass.woff2') format('woff2'),
    url('./font/icon-bass.woff') format('woff'),
    url('./font/icon-bass.ttf') format('truetype'),
    url('./font/icon-bass.svg#.icon-bass') format('svg');
  font-weight: normal;
  font-style: normal;
}
.iui-icon:before {
  display: inline-block;
  font-family: "icon-bass";
  font-style: normal;
  font-weight: normal;
  line-height: 1;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
.iui-icon-arrow-left:before { content: "\EA01" }
.iui-icon-arrow-right:before { content: "\EA02" }
.iui-icon-arrow-down:before { content: "\EA03" }
.iui-icon-km:before { content: "\EA04" }
.iui-icon-task:before { content: "\EA05" }
.iui-icon-project:before { content: "\EA06" }
.iui-icon-moreapp:before { content: "\EA07" }
.iui-icon-calendar:before { content: "\EA08" }
.iui-icon-analytics:before { content: "\EA09" }
.iui-icon-arrow-up:before { content: "\EA11" }
.iui-icon-edit:before { content: "\EA12" }
.iui-icon-trig-down:before { content: "\EA13" }
.iui-icon-trig-up:before { content: "\EA14" }
.iui-icon-arrow-next:before { content: "\EA15" }
.iui-icon-arrow-prev:before { content: "\EA16" }
.iui-icon-archive:before { content: "\EA17" }
.iui-icon-search:before { content: "\EA18" }
.iui-icon-close:before { content: "\EA19" }
.iui-icon-start-round:before { content: "\EA21" }
.iui-icon-flag:before { content: "\EA22" }
.iui-icon-clock:before { content: "\EA23" }
.iui-icon-user:before { content: "\EA24" }
.iui-icon-add-round:before { content: "\EA25" }
.iui-icon-add:before { content: "\EA26" }
.iui-icon-task-check:before { content: "\EA27" }
.iui-icon-return:before { content: "\EA28" }
.iui-icon-notification:before { content: "\EA29" }
.iui-icon-back:before { content: "\EA31" }
.iui-icon-checked:before { content: "\EA32" }
.iui-icon-done:before { content: "\EA33" }
.iui-icon-start:before { content: "\EA34" }
.iui-icon-notification-unread:before { content: "\EA35" }
.iui-icon-warning:before { content: "\EA36" }
.iui-icon-comment:before { content: "\EA37" }
.iui-icon-stop-round:before { content: "\EA38" }
.iui-icon-checkbox:before { content: "\EA39" }
.iui-icon-filetype-doc:before { content: "\EA41"; color: #0a96e5;}
.iui-icon-filetype-pdf:before { content: "\EA42"; color: #e3574d;}
.iui-icon-filetype-folder:before { content: "\EA43"; color: #cdc9c5;}
.iui-icon-filetype-video:before { content: "\EA44"; color: #d94ff5;}
.iui-icon-filetype-music:before { content: "\EA45"; color: #a7d638;}
.iui-icon-filetype-zip:before { content: "\EA46"; color: #9d7120;}
.iui-icon-filetype-image:before { content: "\EA47"; color: #07cfda;}
.iui-icon-filetype-excel:before { content: "\EA48"; color: #1c7044;}
.iui-icon-filetype-default:before { content: "\EA49"; color: #cdc9c5;}
.iui-icon-info:before { content: "\EA51" }
.iui-icon-alpha:before { content: "\EA52" }
.iui-icon-link:before { content: "\EA53" }
.iui-icon-dot:before { content: "\EA54" }
.iui-icon-filetype-ppt:before { content: "\EA55"; color: #d04424;}
.iui-icon-settings:before { content: "\EA56" }
.iui-icon-restore:before { content: "\EA57" }
.iui-icon-delete:before { content: "\EA58" }
.iui-icon-list:before { content: "\EA59" }
.iui-icon-company:before { content: "\EA61" }
.iui-icon-timer-hand:before { content: "\EA62" }
.iui-icon-timer-body:before { content: "\EA63" }
.iui-icon-timer:before { content: "\EA64" }
.iui-icon-list-add:before { content: "\EA65" }
.iui-icon-project-type4:before { content: "\EA66" }
.iui-icon-project-type3:before { content: "\EA67" }
.iui-icon-project-type2:before { content: "\EA68" }
.iui-icon-project-type1:before { content: "\EA69" }
.iui-icon-filter:before { content: "\EA71" }
.iui-icon-category:before { content: "\EA72" }
.iui-icon-process:before { content: "\EA73" }
.iui-icon-paper:before { content: "\EA74" }
.iui-icon-firm:before { content: "\EA75" }
.iui-icon-clerk:before { content: "\EA76" }
.iui-icon-judge:before { content: "\EA77" }
.iui-icon-lawyer:before { content: "\EA78" }
.iui-icon-team:before { content: "\EA79" }
.iui-icon-ilaw:before { content: "\EA81" }
.iui-icon-tools:before { content: "\EA82" }
.iui-icon-customer:before { content: "\EA83" }
.iui-icon-hr:before { content: "\EA84" }
.iui-icon-add-fill:before { content: "\EA85" }
.iui-icon-minus-fill:before { content: "\EA86" }
.iui-icon-checkmark:before { content: "\EA87" }
.iui-icon-stop:before { content: "\EA88" }
.iui-icon-download:before { content: "\EA89" }
.iui-icon-share:before { content: "\EA91" }
.iui-icon-location:before { content: "\EA92" }
.iui-icon-phone:before { content: "\EA93" }
.iui-icon-email:before { content: "\EA94" }
.iui-icon-user-female:before { content: "\EA95" }
.iui-icon-smart:before { content: "\EA96" }
.iui-icon-logout:before { content: "\EA97" }
.iui-icon-chart-bar:before { content: "\EA98" }
.iui-icon-chart-line:before { content: "\EA99" }
.iui-icon-minus-round:before { content: "\EB01" }
.iui-icon-chart-pie:before { content: "\EB02" }
.iui-icon-chart-map:before { content: "\EB03" }
.iui-icon-customer-service:before { content: "\EB04" }
.iui-icon-marker:before { content: "\EB05" }
.iui-icon-copy:before { content: "\EB06" }
.iui-icon-star:before { content: "\EB07" }
.iui-icon-star-fill:before { content: "\EB08" }
.iui-icon-heart:before { content: "\EB09" }
.iui-icon-pin:before { content: "\EB11" }
.iui-icon-required:before { content: "\EB12" }
.iui-icon-customer-surprise:before { content: "\EB13" }
.iui-icon-text:before { content: "\EB14" }
.iui-icon-field-casade:before { content: "\EB15" }
.iui-icon-insert:before { content: "\EB16" }
.iui-icon-case:before { content: "\EB17" }
.iui-icon-attachment:before { content: "\EB18" }
.iui-icon-heart-fill:before { content: "\EB19" }
.iui-icon-trig-right:before { content: "\EB21" }
.iui-icon-trig-left:before { content: "\EB22" }
.iui-icon-bold:before { content: "\EB23" }
.iui-icon-italic:before { content: "\EB24" }
.iui-icon-underline:before { content: "\EB25" }
.iui-icon-plus-square:before { content: "\EB26" }
.iui-icon-minus-square:before { content: "\EB27" }
.iui-icon-chart-bar-h:before { content: "\EB28" }
.iui-icon-task-pad:before { content: "\EB29" }
.iui-icon-schedule:before { content: "\EB31" }
.iui-icon-upload:before { content: "\EB32" }
.iui-icon-tag:before { content: "\EB33" }
.iui-icon-sort:before { content: "\EB34" }
.iui-icon-more:before { content: "\EB35" }
.iui-icon-side-column:before { content: "\EB36" }
.iui-icon-window-fullscreen:before { content: "\EB37" }
.iui-icon-mute:before { content: "\EB38" }
.iui-icon-locked:before { content: "\EB39" }
.iui-icon-spanner:before { content: "\EB41" }
.iui-icon-alarm:before { content: "\EB42" }
.iui-icon-loop:before { content: "\EB43" }
.iui-icon-unlocked:before { content: "\EB44" }
.iui-icon-memo:before { content: "\EB45" }
.iui-icon-emoji:before { content: "\EB52" }
.iui-icon-snap:before {content: "\EB53"}
</style>

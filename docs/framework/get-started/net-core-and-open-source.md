---
title: ".NET Core und Open-Source | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e6bd4655-ce37-4003-8462-468a6fe2c40f
caps.latest.revision: 8
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 6
---
# .NET Core und Open-Source
.NET Core ist eine modulare Version von .NET Framework, die auf plattformübergreifende Portierbarkeit ausgelegt ist, um maximale Wiederverwendbarkeit und gemeinsame Nutzung von Code zu gewährleisten. Darüber hinaus ist .NET Core als Open Source angelegt und akzeptiert Beiträge aus der Community. In diesem Thema werden einige häufig gestellte Fragen zu .NET Core beantwortet und wie man auf die Open\-Source\-Pakete zugreift und zu ihnen beitragen kann.  
  
<a name="BKMK_WhatisNETCore"></a>   
## Was ist .NET Core?  
 Wie zuvor bereits erwähnt, ist .NET Core eine modulare Version von .NET Framework, die auf plattformübergreifende Portierbarkeit ausgelegt ist.  
  
 .NET Core ist plattformübergreifend portierbar, weil es, obwohl es eine Teilmenge des vollständigen .NET Framework ist, die Hauptfunktionen zur Implementierung der App\-Funktionen bereitstellt, die Sie benötigen, sowie zur Wiederverwendung dieses Codes unabhängig von Ihrer Zielplattform. In der Vergangenheit fehlten bei verschiedene Versionen von .NET für unterschiedliche Plattformen gemeinsam genutzte Funktionen für wichtige Aufgaben wie das Lesen lokaler Dateien. Microsoft\-Plattformen, die Sie mit .NET Core als Ziele berücksichtigen können, umfassen traditionelle Desktopversionen von Windows sowie Windows\-Geräte und \-Telefone. Bei Verwendung von Drittanbietertools wie Xamarin sollte .NET Core auch auf IOS\- und Android\-Geräte portierbar sein. Darüber hinaus wird .NET Core bald für Mac\- und Linux\-Betriebssysteme erhältlich sein, um die Ausführung von Web\-Apps auf diesen Systemen zu ermöglichen.  
  
 .NET Core ist modular aufgebaut, weil es über NuGet in kleineren Assemblypaketen veröffentlicht wird. Statt in einer großen Assembly, die die meisten der Kernfunktionalitäten enthält, wird .NET Core in kleineren, funktionsorientierten Pakete zur Verfügung gestellt. Dies ermöglicht ein flexibleres Entwicklungsmodell für uns und ermöglicht es Ihnen, die Teilfunktionen auszuwählen, die Sie für Ihre Apps und Bibliotheken benötigen. Weitere Informationen zu über NuGet veröffentlichten .NET\-Paketen finden Sie unter [.NET Framework und Out\-of\-Band\-Versionen](../../../docs/framework/get-started/the-net-framework-and-out-of-band-releases.md).  
  
 Im Folgenden finden Sie einige häufig gestellte Fragen zu .NET Core.  
  
### Wie kann ich .NET Core am besten nutzen?  
 Für vorhandene Apps ist die Verwendung von portablen Klassenbibliotheken \(Portable Class Libraries, PCL\) und Universal App\-Projekten sowie die Trennung der Geschäftslogik von plattformspezifischem Code die beste Möglichkeit, um .NET Core nutzen und die Wiederverwendbarkeit Ihres Codes zu maximieren. Für Apps sind die Model\-View\-Controller\- \(MVC\) oder die Model View\-ViewModel\-Muster \(MVVM\) eine gute Wahl, um die Migrierbarkeit Ihrer Anwendungen zu .NET Core zu erleichtern.  
  
### Wie wirkt sich .NET Core auf Kompatibilität und Bereitstellung aus?  
 Es gibt ein paar unterschiedliche Szenarios für die Bereitstellung, wobei sich die Bereitstellung aber weiterhin einfach gestalten sollte. .NET Framework wird zusammen mit Windows verteilt und über Microsoft Update aktualisiert – genau wie heute auch. In einigen Fällen wird Ihre App auf dieser Bereitstellung von .NET Framework auf dem Datenträger basieren, während Ihre App in anderen Fällen auf .NET\-Assemblys basieren wird, die zusammen mit dem App\-Paket bereitgestellt werden. Darüber hinaus stellt die Kompatibilität zwischen Versionen immer noch eine hohe Priorität für .NET Framework dar, damit ihre App, wenn sie mit einer neueren Version einer Assembly ausgeführt wird, als der, mit der sie kompiliert wurde, ihr Verhalten unverändert bleibt.  
  
|Szenario|Bereitstellung|  
|--------------|--------------------|  
|Windows\-Desktop\- und ASP.NET\-Apps, die auf Computern unter Windows ausgeführt werden|Die Bereitstellung ist mit der aktuellen identisch. Eine App basiert auf der Installation von .NET Framework auf dem Server oder dem Computer des Benutzers. Wenn .NET Framework nicht installiert ist, wird der Benutzer aufgefordert, es zu installieren. Alternativ können Sie eine Installation von .NET mit der App verketten. Wenn Sie Assemblys aus .NET Core verwenden, die in .NET Framework nicht enthalten sind, sind diese Assemblys im App\-Paket enthalten. Außerdem leitet die App, wenn zwei Versionen derselben Assembly von der gleichen App referenziert werden, auf die neuere Assembly um. Weitere Informationen finden Sie unter [Umleiten von Assemblyversionen auf App-Ebene](../../../docs/framework/configure-apps/redirect-assembly-versions.md#BKMK_Redirectingassemblyversionsattheapplevel) und [Gewusst wie: Aktivieren und Deaktivieren der Bindungsumleitung](../../../docs/framework/configure-apps/how-to-enable-and-disable-automatic-binding-redirection.md).<br /><br /> Weitere Informationen zur .NET\-Bereitstellung finden Sie unter [Handbuch für die Bereitstellung für Entwickler](../../../docs/framework/deployment/deployment-guide-for-developers.md).|  
|Windows\- und Windows Phone\-Apps, die über die Windows und Windows Phone Stores verfügbar sind|Die Bereitstellung ist mit der aktuellen identisch, und Apps verwenden die .NET Framework\-Assemblys, die im Betriebssystem enthalten sind. Wenn Ihre App Funktionen verwendet, die in einer .NET Core\-Assembly veröffentlicht sind, die nicht in .NET Framework enthalten ist, wird die Assembly in das App\-Paket aufgenommen. Wenn die App auf mehrere Versionen derselben Assembly referenziert, verwendet diese App automatisch die neuere Version der Assembly.|  
|ASP.NET Core 5.0\-Apps|.NET Core\-Assemblys sind App\-lokal, was bedeutet, dass die erforderlichen Assemblys zusammen mit dem App\-Paket bereitgestellt werden. Weitere Informationen zu ASP.NET Core 5.0 finden Sie unter [Übersicht über ASP.NET 5](http://www.asp.net/vnext/overview/aspnet-vnext/aspnet-5-overview).|  
|Mit Xamarin\-Tools erstellte Apps, die auf anderen Plattformen ausgeführt werden|Derzeit werden diese Apps mit einem Satz optimierter Mono\-Assemblys bereitgestellt, die zusammen mit dem App\-Paket ausgeliefert werden. Dies könnte sich ändern, wenn mehr .NET Core\-Assemblys als Open Source bereitgestellt werden.|  
  
<a name="BKMK_NETCoreOpenSourcePackages"></a>   
## Open Source\-Pakete von .NET Core  
 Zusätzlich zur Modularisierung von .NET Framework veröffentlicht Microsoft die .NET Core\-Pakete als Open Source auf [GitHub](https://github.com/) unter der [MIT](https://github.com/dotnet/corefx/blob/master/LICENSE)\-Lizenz. Dies bedeutet, dass Sie das Git\-Repository klonen, den Code lesen und kompilieren und Pull\-Anforderungen absenden können, wie für jedes andere Open Source\-Paket, das sich auf GitHub befindet. Aufgrund unserer Engagements für Qualität und Kompatibilität wird jede Pull\-Anforderung sorgfältig ausgewertet, bevor sie akzeptiert wird. Im Folgenden finden Sie einige häufig gestellte Fragen.  
  
### Wie kann ich den Code abrufen und einen Build erstellen?  
 Die .NET Core\-Quellpakete werden auf `GitHub` gespeichert, wobei `Git` als Quellcodeverwaltungssystem verwendet wird. Um auf den Code zuzugreifen und daraus einen Build zu erstellen, sollten Sie über grundlegende Kenntnisse im Umgang mit [Git](http://git-scm.com/), [GitHub](https://github.com/dotnet/corefx) und [Visual Studio](http://msdn.microsoft.com/vstudio/aa718325.aspx) verfügen, aber die folgenden Schritte bieten einige Informationen und Links, die Ihnen den Einstieg erleichtern.  
  
 Informationen zum Einrichten von Git und GitHub finden Sie im Abschnitt zum [Einrichten von Git](https://help.github.com/articles/set-up-git/) auf der GitHub\-Website.  
  
 Für den Zugriff auf den .NET Framework\-Code müssen Sie das Git\-Repository, das den Code enthält, verzweigen und ihn auf Ihren Entwicklungscomputer klonen. Sie können den Code verzweigen, indem Sie durch das Repository navigieren und dann in der rechten oberen Ecke des Browsers auf **Fork** klicken. Sie können die Verzweigung klonen, indem Sie die GitHub\-App oder die Befehlszeile in der GitHub\-Shell verwenden. Um das Repository in der GitHub\-Shell zu klonen, führen Sie diesen Befehl aus:  
  
```  
git clone https://github.com/dotnet/corefx  
```  
  
 Um einen Build des Codes zu erstellen, sollten Sie Visual Studio 2013 installiert haben. Sie können die Projektmappen dann entweder mit Visual Studio 2013 und durch Drücken von F5 öffnen und erstellen, oder Sie erstellen sie in der Befehlszeile mithilfe der Developer\-Eingabeaufforderung. Zum Erstellen über die Eingabeaufforderung öffnen Sie eine Developer\-Eingabeaufforderung, und navigieren Sie zu dem Ordner, in den Sie den Quellcode geklont haben. Geben Sie anschließend Folgendes ein:  
  
```  
build.cmd  
  
```  
  
 Weitere Informationen zum Zugreifen auf die Developer\-Eingabeaufforderung finden Sie unter [Eingabeaufforderungen](../../../docs/framework/tools/developer-command-prompt-for-vs.md).  
  
### Welche Richtlinien gelten für die Einreichung von Code?  
 Bevor wir Ihre Arbeit in die Hauptverzweigung integrieren können, müssen Sie eine [Contributor License Agreement \(CLA\)](https://cla.dotnetfoundation.org/) unterzeichnen.  
  
 Wir akzeptieren Beiträge aus der Community unter Verwendung des Fork\- und Pull\-Modells. Sie sollten den Code verzweigen \(Fork\) und klonen und eine Pull\-Anforderung an die .NET Framework\-Hauptverzweigung senden. Weitere Informationen zu Pull\-Anforderungen finden Sie unter [Verwenden von Pull\-Anforderungen](https://help.github.com/articles/using-pull-requests/). Ausführliche Anleitungen zum Senden einer Pull\-Anforderung finden Sie im [.NET Core\-Mitwirkungshandbuch](https://github.com/dotnet/corefx/wiki/Contributing).  
  
### Warum haben Sie meine Pull\-Anforderung nicht akzeptiert?  
 Wenn wir Ihre Anforderung ablehnen, erhalten Sie eine Begründung, warum wir dies getan haben, aber gehen Sie generell davon aus, dass Microsoft sich sehr stark für die Qualität und Kompatibilität des Codes engagiert. Wenn Ihre Pull\-Anforderung nicht akzeptiert wurde, haben Sie möglicherweise unsere Codierungsrichtlinien nicht eingehalten, nicht ausreichend getestet für Ihren Codebeitrag oder die API\-Kompatibilität verletzt. Darüber hinaus sollten sich Ihre Codeänderungen an unserer Roadmap für .NET Framework orientieren. Codierungsrichtlinien und weitere Informationen finden Sie im [.NET Core\-Mitwirkungshandbuch](https://github.com/dotnet/corefx/wiki/Contributing).  
  
## Siehe auch  
 [.NET ist Open Source](http://blogs.msdn.com/b/dotnet/archive/2014/11/12/net-core-is-open-source.aspx)   
 [.NET Open Source Curah](https://curah.microsoft.com/254870/net-core-open-source)   
 [Übersicht zu ASP.NET 5](http://www.asp.net/vnext/overview/aspnet-vnext/aspnet-5-overview)
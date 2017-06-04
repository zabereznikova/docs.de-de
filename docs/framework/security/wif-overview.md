---
title: "Windows Identity Foundation 4.5 – &#220;bersicht | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5f723345-7270-49e2-b638-b3a34bd40517
caps.latest.revision: 11
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 11
---
# Windows Identity Foundation 4.5 – &#220;bersicht
Windows Identity Foundation 4.5 stellt einen Satz von .NET Framework\-Klassen für das Implementieren von anspruchsbasierter Identität in Anwendungen dar.  Mithilfe dieses Produkts können Sie die Vorteile von Ansprüchen unterstützenden Anwendungen und Diensten leichter nutzen.  WIF 4.5 kann in jeder Webanwendung oder in jedem Webdienst eingesetzt werden, die bzw. der .NET Framework Version 4.5 oder höher verwendet.  WIF ist nur ein Teil der Microsoft\-Softwarefamilie für den Identitätsverbund, die die gemeinsame Branchenvision auf der Grundlage von offenen Standards implementiert.  Der Identitätsverbund umfasst drei Komponenten: [Active Directory®\-Verbunddienste](http://go.microsoft.com/fwlink/?LinkID=247516) \(AD FS\) 2.0, [Microsoft Azure\-Zugriffssteuerungsdienste](http://go.microsoft.com/fwlink/?LinkID=247517) \(ACS\) und WIF.  Zusammen bilden diese drei Komponenten den Kern der neuen anspruchsbasierten Cloudidentität und Zugriffsplattform von Microsoft.  
  
 Weitere Informationen über WIF finden Sie auf der [Windows Identity Foundation\-Website](http://go.microsoft.com/fwlink/?LinkId=149009) \(http:\/\/go.microsoft.com\/fwlink\/?LinkId\=149009\) im Security Developer Center auf MSDN.  Eine Einführung zum Erstellen von Anwendungen mithilfe von WIF finden Sie unter [Programming Windows Identity Foundation](http://go.microsoft.com/fwlink/?LinkId=210158) \(http:\/\/go.microsoft.com\/fwlink\/?LinkId\=210158\) von Vittorio Bertocci \(veröffentlicht von Microsoft Press\).  
  
## WIF 4.5\-Funktionen  
 WIF 4.5 ist ein Framework zur Erstellung identitätsabhängiger Anwendungen.  Das Framework abstrahiert die WS\-Trust\- und WS\-Verbund\-Protokolle und stellt Entwicklern APIs zum Erstellen von Ansprüche unterstützenden Anwendungen und ggf. von Sicherheitstokendiensten \(STS\) bereit.  Anwendungen können WIF verwenden, um die Tokens zu verarbeiten, die von den STS\-Diensten wie AD FS 2.0 und ACS ausgegeben werden, und um identitätsbasierte Entscheidungen für die Webanwendung oder den Webdienst zu treffen.  
  
 WIF 4.5 verfügt über die folgenden Hauptfunktionen:  
  
-   Erstellen von Ansprüche unterstützenden Anwendungen \(Anwendung der vertrauenden Seite\).  WIF unterstützt Entwickler beim Erstellen von Ansprüche unterstützenden Anwendungen.  Zusätzlich zur Bereitstellung eines Anspruchsmodells bietet es Anwendungsentwicklern einen umfassenden Satz von APIs, um Benutzerzugriffsentscheidungen auf Grundlage von Ansprüchen zu unterstützen.  Darüber hinaus stellt WIF Entwicklern konsistente Programmierungsmöglichkeiten zur Verfügung, unabhängig davon, ob sie die Anwendungen in einer ASP.NET\- oder WCF\-Umgebung erstellen.  
  
-   Integrieren von Identitätsdelegierungsunterstützung in Ansprüche unterstützende Anwendungen.  Mit WIF können die Identitäten der ursprünglichen anfordernden Benutzer über verschiedene Dienste hinweg beibehalten werden.  Diese Funktion kann entweder mit der Funktion "ActAs" oder der Funktion "OnBehalfOf" im Framework genutzt werden. Sie bietet Entwicklern außerdem die Möglichkeit, die Ansprüche unterstützenden Anwendungen um die Identitätsdelegierungsunterstützung zu erweitern.  
  
-   Erstellen von benutzerdefinierten STS\-Diensten.  Mit WIF ist es wesentlich einfacher, einen benutzerdefinierten STS zu erstellen, der das WS\-Trust\-Protokoll unterstützt.  Ein solcher STS wird als aktiver STS bezeichnet.  
  
     Außerdem bietet das Framework Unterstützung für das Erstellen eines STS, der den WS\-Verbund unterstützt, um Webbrowserclients zu aktivieren.  Ein solcher STS wird auch als passiver STS bezeichnet.  
  
-   Ein neues Identitäts\- und Zugriffs\-Tool für Visual Studio 11, das es Ihnen ermöglicht, die Anwendung mit anspruchsbasierter Identität zu sichern und Benutzer verschiedener Identitätsanbieter zu akzeptieren.  Sie können dieses WIF\-Tool von folgender URL herunterladen: [http:\/\/go.microsoft.com\/fwlink\/?LinkID\=245849](http://go.microsoft.com/fwlink/?LinkID=245849). Sie können es auch direkt aus Visual Studio 11 herunterladen, indem Sie im Erweiterungs\-Manager nach "Identität" suchen.  Weitere Informationen finden Sie unter [Identitäts\- und Zugriffs\-Tool für Visual Studio 2012](../../../docs/framework/security/identity-and-access-tool-for-vs.md).  
  
 WIF unterstützt die folgenden Hauptszenarien:  
  
-   Verbund.  WIF ermöglicht es, den Verbund zwischen zwei oder mehr Partnern zu aktivieren.  Dieses Szenario können Entwickler mithilfe der Unterstützung für das Erstellen von Ansprüche unterstützenden Anwendungen und für benutzerdefinierte STS umsetzen.  
  
-   Identitätsdelegierung.  Mit WIF können Identitäten über mehrere Dienste hinweg einfach beibehalten werden, damit Entwickler ein Identitätsdelegierungsszenario umsetzen können.  
  
-   Aufwärtsauthentifizierung.  Die Authentifizierungsanforderungen für verschiedene Ressourcen innerhalb einer Anwendung können variieren.  WIF bietet Entwicklern die Möglichkeit, Anwendungen zu erstellen, die inkrementelle Authentifizierungsanforderungen erfordern können \(beispielsweise: ursprüngliche Anmeldung mit Benutzername\/Kennwortauthentifizierung und dann Step\-up auf Smartcardauthentifizierung durchführen\).  
  
 Mithilfe von WIF können Sie leichter von den Vorteilen des anspruchsbasierten Identitätsmodells profitieren.  Weitere Informationen finden Sie im [Windows Identity Foundation\-Whitepaper für Entwickler](http://go.microsoft.com/fwlink/?LinkId=122266).
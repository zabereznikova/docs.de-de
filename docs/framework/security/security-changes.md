---
title: "&#196;nderungen der Sicherheit in .NET Framework | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "AllowPartiallyTrustedCallers-Attribut"
  - ".NET Framework 4, Sicherheitsänderungen"
  - ".NET Framework-Sicherheit"
  - "Sicherheitstransparenter Code"
  - "Sicherheitsrelevanter Code"
  - "Codezugriffssicherheit, Änderungen"
ms.assetid: 5e87881c-9c13-4b52-8ad1-e34bb46e8aaa
caps.latest.revision: 52
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 52
---
# &#196;nderungen der Sicherheit in .NET Framework
Die wichtigste Änderung im Hinblick auf die Sicherheit in [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] betrifft starke Namen. Eine Beschreibung dieser Änderungen finden Sie unter [Verbesserte starke Namen](../../../docs/framework/app-domains/enhanced-strong-naming.md).  
  
 .NET Framework stellt ein Sicherheitsmodell mit zwei Ebenen für verwaltete Anwendungen bereit.[!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]\-Apps werden in einem Windows\-Sicherheitscontainer ausgeführt, der den Zugriff auf Ressourcen beschränkt. Innerhalb dieses Containers werden verwaltete Anwendungen mit voller Vertrauenswürdigkeit ausgeführt. Im Hinblick auf die Codezugriffssicherheit \(Code Access Security, CAS\) haben Entwickler keine Möglichkeit, Berechtigungen heraufstufen. Informationen zu den von Windows gewährten Berechtigungen finden Sie im Windows Dev Center unter [Deklaration der App\-Funktionen \(Windows Store\-Apps\)](http://go.microsoft.com/fwlink/?LinkId=230436). Informationen zum Erstellen einer [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]\-App finden Sie unter [Create your first Windows Runtime app using C\# or Visual Basic](http://go.microsoft.com/fwlink/?LinkId=230461) \(Erstellen Ihrer ersten Windows\-Runtime\-App mit C\# oder Visual Basic\).
---
title: Änderungen der Sicherheit in .NET Framework
ms.date: 03/30/2017
helpviewer_keywords:
- Allow Partially Trusted Callers attribute
- .NET Framework 4, security changes
- .NET Framework security
- security-transparent code
- security-critical code
- code access security, changes
ms.assetid: 5e87881c-9c13-4b52-8ad1-e34bb46e8aaa
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 84e80b99ee6d872714180e73354d20770c21e144
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33400080"
---
# <a name="security-changes-in-the-net-framework"></a>Änderungen der Sicherheit in .NET Framework
Die wichtigste Änderung im Hinblick auf die Sicherheit in [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] betrifft starke Namen. Eine Beschreibung dieser Änderungen finden Sie unter [Enhanced Strong Naming](../../../docs/framework/app-domains/enhanced-strong-naming.md) .  
  
 .NET Framework stellt ein Sicherheitsmodell mit zwei Ebenen für verwaltete Anwendungen bereit. [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] -Apps werden in einem Windows-Sicherheitscontainer ausgeführt, der den Zugriff auf Ressourcen beschränkt. Innerhalb dieses Containers werden verwaltete Anwendungen mit voller Vertrauenswürdigkeit ausgeführt. Im Hinblick auf die Codezugriffssicherheit (Code Access Security, CAS) haben Entwickler keine Möglichkeit, Berechtigungen heraufstufen. Informationen zu den von Windows gewährten Berechtigungen finden Sie im Windows Dev Center unter [Deklaration der App-Funktionen (Windows Store-Apps)](http://go.microsoft.com/fwlink/?LinkId=230436) . Informationen zum Erstellen einer [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] -App finden Sie unter [Create your first Windows Runtime app using C# or Visual Basic](http://go.microsoft.com/fwlink/?LinkId=230461)(Erstellen Ihrer ersten Windows-Runtime-App mit C# oder Visual Basic).

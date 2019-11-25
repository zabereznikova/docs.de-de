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
ms.openlocfilehash: af2869e5ca3b41778c094b7a78a9493e74868811
ms.sourcegitcommit: 81ad1f09b93f3b3e6706a7f2e4ddf50ef229ea3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/20/2019
ms.locfileid: "74204508"
---
# <a name="security-changes-in-the-net-framework"></a>Änderungen der Sicherheit in .NET Framework

The most important change to security in the .NET Framework 4.5 is in strong naming. Eine Beschreibung dieser Änderungen finden Sie unter [Enhanced Strong Naming](../../standard/assembly/enhanced-strong-naming.md) .  
  
.NET Framework stellt ein Sicherheitsmodell mit zwei Ebenen für verwaltete Anwendungen bereit. Windows 8.x Store apps run in a Windows security container that limits access to resources. Innerhalb dieses Containers werden verwaltete Anwendungen mit voller Vertrauenswürdigkeit ausgeführt. Im Hinblick auf die Codezugriffssicherheit (Code Access Security, CAS) haben Entwickler keine Möglichkeit, Berechtigungen heraufstufen. Informationen zu den von Windows gewährten Berechtigungen finden Sie im Windows Dev Center unter [Deklaration der App-Funktionen (Windows Store-Apps)](https://go.microsoft.com/fwlink/?LinkId=230436) . For information about creating a Windows 8.x Store app, see [Create your first Windows Store app using C# or Visual Basic](https://go.microsoft.com/fwlink/?LinkId=230461).

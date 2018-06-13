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
# <a name="security-changes-in-the-net-framework"></a><span data-ttu-id="72723-102">Änderungen der Sicherheit in .NET Framework</span><span class="sxs-lookup"><span data-stu-id="72723-102">Security Changes in the .NET Framework</span></span>
<span data-ttu-id="72723-103">Die wichtigste Änderung im Hinblick auf die Sicherheit in [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] betrifft starke Namen.</span><span class="sxs-lookup"><span data-stu-id="72723-103">The most important change to security in the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] is in strong naming.</span></span> <span data-ttu-id="72723-104">Eine Beschreibung dieser Änderungen finden Sie unter [Enhanced Strong Naming](../../../docs/framework/app-domains/enhanced-strong-naming.md) .</span><span class="sxs-lookup"><span data-stu-id="72723-104">See [Enhanced Strong Naming](../../../docs/framework/app-domains/enhanced-strong-naming.md) for a description of those changes.</span></span>  
  
 <span data-ttu-id="72723-105">.NET Framework stellt ein Sicherheitsmodell mit zwei Ebenen für verwaltete Anwendungen bereit.</span><span class="sxs-lookup"><span data-stu-id="72723-105">The .NET Framework provides a two-tier security model for managed applications.</span></span> [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]<span data-ttu-id="72723-106"> -Apps werden in einem Windows-Sicherheitscontainer ausgeführt, der den Zugriff auf Ressourcen beschränkt.</span><span class="sxs-lookup"><span data-stu-id="72723-106"> apps run in a Windows security container that limits access to resources.</span></span> <span data-ttu-id="72723-107">Innerhalb dieses Containers werden verwaltete Anwendungen mit voller Vertrauenswürdigkeit ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="72723-107">Within that container, managed applications run fully trusted.</span></span> <span data-ttu-id="72723-108">Im Hinblick auf die Codezugriffssicherheit (Code Access Security, CAS) haben Entwickler keine Möglichkeit, Berechtigungen heraufstufen.</span><span class="sxs-lookup"><span data-stu-id="72723-108">From a code access security (CAS) perspective, there is nothing a developer can do to elevate privileges.</span></span> <span data-ttu-id="72723-109">Informationen zu den von Windows gewährten Berechtigungen finden Sie im Windows Dev Center unter [Deklaration der App-Funktionen (Windows Store-Apps)](http://go.microsoft.com/fwlink/?LinkId=230436) .</span><span class="sxs-lookup"><span data-stu-id="72723-109">For information about the privileges granted by Windows, see [App capability declarations (Windows Store apps)](http://go.microsoft.com/fwlink/?LinkId=230436) in the Windows Dev Center.</span></span> <span data-ttu-id="72723-110">Informationen zum Erstellen einer [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] -App finden Sie unter [Create your first Windows Runtime app using C# or Visual Basic](http://go.microsoft.com/fwlink/?LinkId=230461)(Erstellen Ihrer ersten Windows-Runtime-App mit C# oder Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="72723-110">For information about creating a [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] app, see [Create your first Windows Store app using C# or Visual Basic](http://go.microsoft.com/fwlink/?LinkId=230461).</span></span>

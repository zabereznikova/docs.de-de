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
ms.openlocfilehash: c62a469b3e31283e5790c747092a8fe504ef8c2a
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2018
ms.locfileid: "45615481"
---
# <a name="security-changes-in-the-net-framework"></a><span data-ttu-id="18d3e-102">Änderungen der Sicherheit in .NET Framework</span><span class="sxs-lookup"><span data-stu-id="18d3e-102">Security Changes in the .NET Framework</span></span>
<span data-ttu-id="18d3e-103">Die wichtigste Änderung im Hinblick auf die Sicherheit in [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] betrifft starke Namen.</span><span class="sxs-lookup"><span data-stu-id="18d3e-103">The most important change to security in the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] is in strong naming.</span></span> <span data-ttu-id="18d3e-104">Eine Beschreibung dieser Änderungen finden Sie unter [Enhanced Strong Naming](../../../docs/framework/app-domains/enhanced-strong-naming.md) .</span><span class="sxs-lookup"><span data-stu-id="18d3e-104">See [Enhanced Strong Naming](../../../docs/framework/app-domains/enhanced-strong-naming.md) for a description of those changes.</span></span>  
  
 <span data-ttu-id="18d3e-105">.NET Framework stellt ein Sicherheitsmodell mit zwei Ebenen für verwaltete Anwendungen bereit.</span><span class="sxs-lookup"><span data-stu-id="18d3e-105">The .NET Framework provides a two-tier security model for managed applications.</span></span> [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]<span data-ttu-id="18d3e-106"> -Apps werden in einem Windows-Sicherheitscontainer ausgeführt, der den Zugriff auf Ressourcen beschränkt.</span><span class="sxs-lookup"><span data-stu-id="18d3e-106"> apps run in a Windows security container that limits access to resources.</span></span> <span data-ttu-id="18d3e-107">Innerhalb dieses Containers werden verwaltete Anwendungen mit voller Vertrauenswürdigkeit ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="18d3e-107">Within that container, managed applications run fully trusted.</span></span> <span data-ttu-id="18d3e-108">Im Hinblick auf die Codezugriffssicherheit (Code Access Security, CAS) haben Entwickler keine Möglichkeit, Berechtigungen heraufstufen.</span><span class="sxs-lookup"><span data-stu-id="18d3e-108">From a code access security (CAS) perspective, there is nothing a developer can do to elevate privileges.</span></span> <span data-ttu-id="18d3e-109">Informationen zu den von Windows gewährten Berechtigungen finden Sie im Windows Dev Center unter [Deklaration der App-Funktionen (Windows Store-Apps)](https://go.microsoft.com/fwlink/?LinkId=230436) .</span><span class="sxs-lookup"><span data-stu-id="18d3e-109">For information about the privileges granted by Windows, see [App capability declarations (Windows Store apps)](https://go.microsoft.com/fwlink/?LinkId=230436) in the Windows Dev Center.</span></span> <span data-ttu-id="18d3e-110">Informationen zum Erstellen einer [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] -App finden Sie unter [Create your first Windows Runtime app using C# or Visual Basic](https://go.microsoft.com/fwlink/?LinkId=230461)(Erstellen Ihrer ersten Windows-Runtime-App mit C# oder Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="18d3e-110">For information about creating a [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] app, see [Create your first Windows Store app using C# or Visual Basic](https://go.microsoft.com/fwlink/?LinkId=230461).</span></span>

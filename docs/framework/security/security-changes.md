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
# <a name="security-changes-in-the-net-framework"></a><span data-ttu-id="ce671-102">Änderungen der Sicherheit in .NET Framework</span><span class="sxs-lookup"><span data-stu-id="ce671-102">Security Changes in the .NET Framework</span></span>

<span data-ttu-id="ce671-103">Die wichtigste Änderung an der Sicherheit in der .NET Framework 4,5 ist die starke Benennung.</span><span class="sxs-lookup"><span data-stu-id="ce671-103">The most important change to security in the .NET Framework 4.5 is in strong naming.</span></span> <span data-ttu-id="ce671-104">Eine Beschreibung dieser Änderungen finden Sie unter [Enhanced Strong Naming](../../standard/assembly/enhanced-strong-naming.md) .</span><span class="sxs-lookup"><span data-stu-id="ce671-104">See [Enhanced Strong Naming](../../standard/assembly/enhanced-strong-naming.md) for a description of those changes.</span></span>  
  
<span data-ttu-id="ce671-105">.NET Framework stellt ein Sicherheitsmodell mit zwei Ebenen für verwaltete Anwendungen bereit.</span><span class="sxs-lookup"><span data-stu-id="ce671-105">The .NET Framework provides a two-tier security model for managed applications.</span></span> <span data-ttu-id="ce671-106">Windows 8. x Store-Apps werden in einem Windows-Sicherheitscontainer ausgeführt, der den Zugriff auf Ressourcen einschränkt.</span><span class="sxs-lookup"><span data-stu-id="ce671-106">Windows 8.x Store apps run in a Windows security container that limits access to resources.</span></span> <span data-ttu-id="ce671-107">Innerhalb dieses Containers werden verwaltete Anwendungen mit voller Vertrauenswürdigkeit ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ce671-107">Within that container, managed applications run fully trusted.</span></span> <span data-ttu-id="ce671-108">Im Hinblick auf die Codezugriffssicherheit (Code Access Security, CAS) haben Entwickler keine Möglichkeit, Berechtigungen heraufstufen.</span><span class="sxs-lookup"><span data-stu-id="ce671-108">From a code access security (CAS) perspective, there is nothing a developer can do to elevate privileges.</span></span> <span data-ttu-id="ce671-109">Informationen zu den von Windows gewährten Berechtigungen finden Sie im Windows Dev Center unter [Deklaration der App-Funktionen (Windows Store-Apps)](https://go.microsoft.com/fwlink/?LinkId=230436) .</span><span class="sxs-lookup"><span data-stu-id="ce671-109">For information about the privileges granted by Windows, see [App capability declarations (Windows Store apps)](https://go.microsoft.com/fwlink/?LinkId=230436) in the Windows Dev Center.</span></span> <span data-ttu-id="ce671-110">Weitere Informationen zum Erstellen einer Windows 8. x Store-App finden Sie unter [Erstellen Ihrer ersten Windows Store C# -App mithilfe von oder Visual Basic](https://go.microsoft.com/fwlink/?LinkId=230461).</span><span class="sxs-lookup"><span data-stu-id="ce671-110">For information about creating a Windows 8.x Store app, see [Create your first Windows Store app using C# or Visual Basic](https://go.microsoft.com/fwlink/?LinkId=230461).</span></span>

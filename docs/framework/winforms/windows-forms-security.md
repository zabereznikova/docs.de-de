---
title: "Sicherheit in Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- designer access security [Windows Forms]
- permissions [Windows Forms], Windows Forms
- Windows Forms, security
- security [Windows Forms]
- access control [Windows Forms], Windows Forms
- security policy [Windows Forms], Windows Forms
ms.assetid: 932d438a-5285-46d8-a958-8c93d0ad6cae
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8bd9b87fdfa54a6f9bf53e4fa897106257b4c625
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="windows-forms-security"></a><span data-ttu-id="41294-102">Sicherheit in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="41294-102">Windows Forms Security</span></span>
<span data-ttu-id="41294-103">Windows Forms bietet ein Sicherheitsmodell, das Code-basierte (Sicherheit) festgelegte Ebenen für Code kann unabhängig von der Benutzer, den Code ausführt, ist.</span><span class="sxs-lookup"><span data-stu-id="41294-103">Windows Forms features a security model that is code-based (security levels are set for code, regardless of the user running the code).</span></span> <span data-ttu-id="41294-104">Dies erfolgt zusätzlich zu Sicherheit Schemas, die bereits auf Ihrem Computer vorhanden sein können.</span><span class="sxs-lookup"><span data-stu-id="41294-104">This is in addition to any security schemas that may be in place already on your computer system.</span></span> <span data-ttu-id="41294-105">Diese können in den Browser (z. B. die Zone-basierte Sicherheit in Internet Explorer verfügbar) oder des Betriebssystems (z. B. die Anmeldeinformationen-basierte Sicherheit von Windows NT) umfassen.</span><span class="sxs-lookup"><span data-stu-id="41294-105">These can include those in the browser (such as the zone-based security available in Internet Explorer) or the operating system (such as the credential-based security of Windows NT).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="41294-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="41294-106">In This Section</span></span>  
 [<span data-ttu-id="41294-107">Übersicht über die Sicherheit in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="41294-107">Security in Windows Forms Overview</span></span>](../../../docs/framework/winforms/security-in-windows-forms-overview.md)  
 <span data-ttu-id="41294-108">Eine kurze Erläuterung, dass das .NET Framework-Sicherheitsmodell und die grundlegenden Schritte erforderlich, um sicherzustellen, dass die Windows Forms in Ihrer Anwendung gesichert werden.</span><span class="sxs-lookup"><span data-stu-id="41294-108">Briefly explains the .NET Framework security model and the basic steps necessary to ensure the Windows Forms in your application are secure.</span></span>  
  
 [<span data-ttu-id="41294-109">Mehr Sicherheit beim Datei- und Datenzugriff in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="41294-109">More Secure File and Data Access in Windows Forms</span></span>](../../../docs/framework/winforms/more-secure-file-and-data-access-in-windows-forms.md)  
 <span data-ttu-id="41294-110">Beschreibt, wie Dateien und Daten in einer teilweise vertrauenswürdigen Umgebung zugreifen.</span><span class="sxs-lookup"><span data-stu-id="41294-110">Describes how to access files and data in a semi-trusted environment.</span></span>  
  
 [<span data-ttu-id="41294-111">Mehr Sicherheit beim Drucken in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="41294-111">More Secure Printing in Windows Forms</span></span>](../../../docs/framework/winforms/more-secure-printing-in-windows-forms.md)  
 <span data-ttu-id="41294-112">Beschreibt, wie in einer teilweise vertrauenswürdigen Umgebung Druckfeatures zugegriffen.</span><span class="sxs-lookup"><span data-stu-id="41294-112">Describes how to access printing features in a semi-trusted environment.</span></span>  
  
 [<span data-ttu-id="41294-113">Weitere Überlegungen zur Sicherheit in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="41294-113">Additional Security Considerations in Windows Forms</span></span>](../../../docs/framework/winforms/additional-security-considerations-in-windows-forms.md)  
 <span data-ttu-id="41294-114">Beschreibt Fenstern, verwenden der Zwischenablage und das Aufrufen von nicht verwaltetem Code in einer teilweise vertrauenswürdigen Umgebung.</span><span class="sxs-lookup"><span data-stu-id="41294-114">Describes performing window manipulation, using the Clipboard, and making calls to unmanaged code in a semi-trusted environment.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="41294-115">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="41294-115">Related Sections</span></span>  
 [<span data-ttu-id="41294-116">NIB: Standardsicherheitsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="41294-116">NIB: Default Security Policy</span></span>](http://msdn.microsoft.com/library/2c086873-0894-4f4d-8f7e-47427c1a3b55)  
 <span data-ttu-id="41294-117">Listet die Standardberechtigungen, die in die volle Vertrauenswürdigkeit, Lokales Intranet und Internet Berechtigungssätze gewährt.</span><span class="sxs-lookup"><span data-stu-id="41294-117">Lists the default permissions granted in the Full Trust, Local Intranet, and Internet permission sets.</span></span>  
  
 [<span data-ttu-id="41294-118">NIB: Allgemein Security Policy-Verwaltung</span><span class="sxs-lookup"><span data-stu-id="41294-118">NIB: General Security Policy Administration</span></span>](http://msdn.microsoft.com/library/5121fe35-f0e3-402c-94ab-4f35b0a87b4b)  
 <span data-ttu-id="41294-119">Bietet Informationen zum Verwalten von der .NET Framework-Sicherheitsrichtlinie und erhöhen von Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="41294-119">Gives information about the administering the .NET Framework security policy and elevating permissions.</span></span>  
  
 [<span data-ttu-id="41294-120">Problematische Berechtigungen und richtlinienverwaltung</span><span class="sxs-lookup"><span data-stu-id="41294-120">Dangerous Permissions and Policy Administration</span></span>](../../../docs/framework/misc/dangerous-permissions-and-policy-administration.md)  
 <span data-ttu-id="41294-121">Erläutert einige der.NET Framework-Berechtigungen, die potenziell das Sicherheitssystem umgangen werden, ermöglichen können.</span><span class="sxs-lookup"><span data-stu-id="41294-121">Discusses some of the.NET Framework permissions that can potentially allow the security system to be circumvented.</span></span>  
  
 [<span data-ttu-id="41294-122">Richtlinien für das Schreiben von sicherem Code</span><span class="sxs-lookup"><span data-stu-id="41294-122">Secure Coding Guidelines</span></span>](../../../docs/standard/security/secure-coding-guidelines.md)  
 <span data-ttu-id="41294-123">Enthält Links zu Themen, in denen die bewährten Methoden zum Schreiben von sicheren Code für .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="41294-123">Links to topics that explain the best practices for securely writing code against the .NET Framework.</span></span>  
  
 [<span data-ttu-id="41294-124">NIB: Anfordern von Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="41294-124">NIB: Requesting Permissions</span></span>](http://msdn.microsoft.com/library/0447c49d-8cba-45e4-862c-ff0b59bebdc2)  
 <span data-ttu-id="41294-125">Erläutert die Verwendung von Attributen, die der Laufzeit wissen, welche Berechtigungen Code ausgeführt werden muss.</span><span class="sxs-lookup"><span data-stu-id="41294-125">Discusses the use of attributes to let the runtime know what permissions your code needs to run.</span></span>  
  
 [<span data-ttu-id="41294-126">Schlüsselbegriffe der Sicherheit</span><span class="sxs-lookup"><span data-stu-id="41294-126">Key Security Concepts</span></span>](../../../docs/standard/security/key-security-concepts.md)  
 <span data-ttu-id="41294-127">Links zu Themen, die die grundlegenden Aspekte der codesicherheit abdecken.</span><span class="sxs-lookup"><span data-stu-id="41294-127">Links to topics that cover the basic aspects of code security.</span></span>  
  
 [<span data-ttu-id="41294-128">Grundlagen der Codezugriffssicherheit</span><span class="sxs-lookup"><span data-stu-id="41294-128">Code Access Security Basics</span></span>](../../../docs/framework/misc/code-access-security-basics.md)  
 <span data-ttu-id="41294-129">Erläutert die Grundlagen der Arbeit mit .NET Framework Sicherheitsrichtlinie von Zeit ausführen.</span><span class="sxs-lookup"><span data-stu-id="41294-129">Discusses the basics of working with the .NET Framework run time security policy.</span></span>  
  
 [<span data-ttu-id="41294-130">NIB: Bestimmen des Zeitpunkts für die Sicherheitsrichtlinien ändern</span><span class="sxs-lookup"><span data-stu-id="41294-130">NIB: Determining When to Modify Security Policy</span></span>](http://msdn.microsoft.com/library/af749b17-e461-409d-84b9-a3d44789db16)  
 <span data-ttu-id="41294-131">Erläutert, wie Sie feststellen, wann Ihre Anwendungen von der Standardsicherheitsrichtlinie voneinander abweichen müssen.</span><span class="sxs-lookup"><span data-stu-id="41294-131">Explains how to determine when your applications need to diverge from the default security policy.</span></span>  
  
 [<span data-ttu-id="41294-132">NIB: Bereitstellen von Sicherheitsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="41294-132">NIB: Deploying Security Policy</span></span>](http://msdn.microsoft.com/library/f936c1e5-033b-4bd9-a3bd-a39ba733a681)  
 <span data-ttu-id="41294-133">Erläutert die beste Art und Weise zum Bereitstellen von Änderungen von Sicherheitsrichtlinien an.</span><span class="sxs-lookup"><span data-stu-id="41294-133">Discusses the best manner for deploying security policy changes.</span></span>

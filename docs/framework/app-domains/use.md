---
title: Verwenden von Anwendungsdomänen
description: Verwenden Sie Anwendungsdomänen. Diese stellen eine Isolationseinheit für die Common Language Runtime (CLR) bereit. Anwendungsdomänen werden in einem Prozess erstellt und ausgeführt.
ms.date: 03/30/2017
helpviewer_keywords:
- application domains, about
- common language runtime, application domains
- runtime, application domains
ms.assetid: c6d99815-e022-4d2c-9420-1d7ab5b9d504
ms.openlocfilehash: 36bfc60a55c8b0374a7e542b590aa7c030ceaed6
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96272266"
---
# <a name="using-application-domains"></a><span data-ttu-id="58279-104">Verwenden von Anwendungsdomänen</span><span class="sxs-lookup"><span data-stu-id="58279-104">Using Application Domains</span></span>

<span data-ttu-id="58279-105">Anwendungsdomänen stellen eine Isolationseinheit für die Common Language Runtime (CLR) bereit.</span><span class="sxs-lookup"><span data-stu-id="58279-105">Application domains provide a unit of isolation for the common language runtime.</span></span> <span data-ttu-id="58279-106">Sie werden in einem Prozess erstellt und dort ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="58279-106">They are created and run inside a process.</span></span> <span data-ttu-id="58279-107">Anwendungsdomänen werden normalerweise von einem Runtimehost erstellt. Dabei handelt es sich um eine Anwendung, die dafür verantwortlich ist, die Runtime in einen Prozess zu laden und Benutzercode innerhalb einer Anwendungsdomäne auszuführen.</span><span class="sxs-lookup"><span data-stu-id="58279-107">Application domains are usually created by a runtime host, which is an application responsible for loading the runtime into a process and executing user code within an application domain.</span></span> <span data-ttu-id="58279-108">Der Runtimehost erstellt einen Prozess und eine Standardanwendungsdomäne und führt darin verwalteten Code aus.</span><span class="sxs-lookup"><span data-stu-id="58279-108">The runtime host creates a process and a default application domain, and runs managed code inside it.</span></span> <span data-ttu-id="58279-109">Runtimehosts sind z.B. ASP.NET, Microsoft Internet Explorer und Windows-Shell.</span><span class="sxs-lookup"><span data-stu-id="58279-109">Runtime hosts include ASP.NET, Microsoft Internet Explorer, and the Windows shell.</span></span>  
  
<span data-ttu-id="58279-110">Für die meisten Anwendungen müssen Sie nicht Ihre eigene Anwendungsdomäne erstellen. Der Runtimehost erstellt alle erforderlichen Anwendungsdomänen für Sie.</span><span class="sxs-lookup"><span data-stu-id="58279-110">For most applications, you do not need to create your own application domain; the runtime host creates any necessary application domains for you.</span></span> <span data-ttu-id="58279-111">Sie können aber zusätzliche Anwendungsdomänen erstellen und konfigurieren, wenn Ihre Anwendung Code isolieren oder DLLs verwenden und entladen muss.</span><span class="sxs-lookup"><span data-stu-id="58279-111">However, you can create and configure additional application domains if your application needs to isolate code or to use and unload DLLs.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="58279-112">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="58279-112">In This Section</span></span>  

[<span data-ttu-id="58279-113">How to: Erstellen einer Anwendungsdomäne</span><span class="sxs-lookup"><span data-stu-id="58279-113">How to: Create an Application Domain</span></span>](how-to-create-an-application-domain.md)  
<span data-ttu-id="58279-114">Erläutert, wie Sie eine Anwendungsdomäne programmgesteuert erstellen</span><span class="sxs-lookup"><span data-stu-id="58279-114">Describes how to programmatically create an application domain.</span></span>  
  
[<span data-ttu-id="58279-115">How to: Entladen einer Anwendungsdomäne</span><span class="sxs-lookup"><span data-stu-id="58279-115">How to: Unload an Application Domain</span></span>](how-to-unload-an-application-domain.md)  
<span data-ttu-id="58279-116">Erläutert, wie Sie eine Anwendungsdomäne programmgesteuert entladen</span><span class="sxs-lookup"><span data-stu-id="58279-116">Describes how to programmatically unload an application domain.</span></span>  
  
[<span data-ttu-id="58279-117">How to: Konfigurieren einer Anwendungsdomäne</span><span class="sxs-lookup"><span data-stu-id="58279-117">How to: Configure an Application Domain</span></span>](how-to-configure-an-application-domain.md)  
<span data-ttu-id="58279-118">Führt Sie in die Konfiguration einer Anwendungsdomäne ein</span><span class="sxs-lookup"><span data-stu-id="58279-118">Provides an introduction to configuring an application domain.</span></span>  
  
[<span data-ttu-id="58279-119">Abrufen von Setupinformationen aus einer Anwendungsdomäne</span><span class="sxs-lookup"><span data-stu-id="58279-119">Retrieving Setup Information from an Application Domain</span></span>](retrieve-setup-information.md)  
<span data-ttu-id="58279-120">Erläutert, wie Sie Setupinformationen aus einer Anwendungsdomäne abrufen können</span><span class="sxs-lookup"><span data-stu-id="58279-120">Describes how to retrieve setup information from an application domain.</span></span>  
  
[<span data-ttu-id="58279-121">How to: Laden von Assemblys in eine Anwendungsdomäne</span><span class="sxs-lookup"><span data-stu-id="58279-121">How to: Load Assemblies into an Application Domain</span></span>](how-to-load-assemblies-into-an-application-domain.md)  
<span data-ttu-id="58279-122">Erläutert wie Sie eine Assembly in eine Anwendungsdomäne laden können</span><span class="sxs-lookup"><span data-stu-id="58279-122">Describes how to load an assembly into an application domain.</span></span>  
  
[<span data-ttu-id="58279-123">How to: Abrufen von Typ- und Memberinformationen aus einer Assembly</span><span class="sxs-lookup"><span data-stu-id="58279-123">How to: Obtain Type and Member Information from an Assembly</span></span>](../reflection-and-codedom/get-type-member-information.md)  
<span data-ttu-id="58279-124">Erläutert, wie Sie Informationen zu einer Assembly abrufen können</span><span class="sxs-lookup"><span data-stu-id="58279-124">Describes how to retrieve information about an assembly.</span></span>  
  
[<span data-ttu-id="58279-125">Erstellen von Schattenkopien von Assemblys</span><span class="sxs-lookup"><span data-stu-id="58279-125">Shadow Copying Assemblies</span></span>](shadow-copy-assemblies.md)  
<span data-ttu-id="58279-126">Erläutert, wie Sie Assemblys mit Schattenkopien aktualisieren können, während diese gerade verwendet werden, und wie Sie Schattenkopien konfigurieren können</span><span class="sxs-lookup"><span data-stu-id="58279-126">Describes how shadow copying allows updates to assemblies while they are in use, and how to configure shadow copying.</span></span>  
  
[<span data-ttu-id="58279-127">How to: Empfangen von Ausnahmebenachrichtigungen (erste Chance)</span><span class="sxs-lookup"><span data-stu-id="58279-127">How to: Receive First-Chance Exception Notifications</span></span>](how-to-receive-first-chance-exception-notifications.md)  
<span data-ttu-id="58279-128">Erläutert, wie Sie eine Benachrichtigung bezüglich einer ausgelösten Ausnahme abrufen können, bevor die CLR mit dem Suchen nach Ausnahmehandlern beginnt.</span><span class="sxs-lookup"><span data-stu-id="58279-128">Explains how you can receive a notification that an exception has been thrown, before the common language runtime has begun searching for exception handlers.</span></span>  
  
[<span data-ttu-id="58279-129">Auflösen beim Laden von Assemblys</span><span class="sxs-lookup"><span data-stu-id="58279-129">Resolving Assembly Loads</span></span>](../../standard/assembly/resolve-loads.md)  
<span data-ttu-id="58279-130">Führt Sie in das Verwenden des Ereignisses <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> ein, um fehlgeschlagene Assemblyladevorgänge aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="58279-130">Provides guidance on using the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event to resolve assembly load failures.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="58279-131">Referenz</span><span class="sxs-lookup"><span data-stu-id="58279-131">Reference</span></span>  

<xref:System.AppDomain>  
<span data-ttu-id="58279-132">Stellt eine Anwendungsdomäne dar</span><span class="sxs-lookup"><span data-stu-id="58279-132">Represents an application domain.</span></span> <span data-ttu-id="58279-133">Bietet Methoden zum Erstellen und Steuern von Anwendungsdomänen</span><span class="sxs-lookup"><span data-stu-id="58279-133">Provides methods for creating and controlling application domains.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="58279-134">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="58279-134">Related Sections</span></span>  

[<span data-ttu-id="58279-135">Assemblys in .NET</span><span class="sxs-lookup"><span data-stu-id="58279-135">Assemblies in .NET</span></span>](../../standard/assembly/index.md)  
<span data-ttu-id="58279-136">Gibt einen Überblick über von Assemblys ausgeführte Funktionen</span><span class="sxs-lookup"><span data-stu-id="58279-136">Provides an overview of the functions performed by assemblies.</span></span>  
  
[<span data-ttu-id="58279-137">Programmieren mit Assemblys</span><span class="sxs-lookup"><span data-stu-id="58279-137">Programming with Assemblies</span></span>](../../standard/assembly/index.md)  
<span data-ttu-id="58279-138">Beschreibt das Erstellen, Signieren und Festlegen von Attributen für Assemblys.</span><span class="sxs-lookup"><span data-stu-id="58279-138">Describes how to create, sign, and set attributes on assemblies.</span></span>  
  
[<span data-ttu-id="58279-139">Ausgeben von dynamischen Methoden und Assemblys</span><span class="sxs-lookup"><span data-stu-id="58279-139">Emitting Dynamic Methods and Assemblies</span></span>](../reflection-and-codedom/emitting-dynamic-methods-and-assemblies.md)  
<span data-ttu-id="58279-140">Beschreibt das Erstellen dynamischer Assemblys.</span><span class="sxs-lookup"><span data-stu-id="58279-140">Describes how to create dynamic assemblies.</span></span>  
  
[<span data-ttu-id="58279-141">Anwendungsdomänen</span><span class="sxs-lookup"><span data-stu-id="58279-141">Application Domains</span></span>](application-domains.md)  
<span data-ttu-id="58279-142">Bietet eine konzeptionelle Übersicht über Anwendungsdomänen.</span><span class="sxs-lookup"><span data-stu-id="58279-142">Provides a conceptual overview of application domains.</span></span>  
  
[<span data-ttu-id="58279-143">Übersicht über Reflektion</span><span class="sxs-lookup"><span data-stu-id="58279-143">Reflection Overview</span></span>](../reflection-and-codedom/reflection.md)  
<span data-ttu-id="58279-144">Beschreibt, wie die **Reflektion**-Klasse verwendet wird, um Informationen zu einer Assembly abzurufen.</span><span class="sxs-lookup"><span data-stu-id="58279-144">Describes how to use the **Reflection** class to obtain information about an assembly.</span></span>

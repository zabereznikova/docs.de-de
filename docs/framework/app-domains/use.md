---
title: Verwenden von Anwendungsdomänen
ms.date: 03/30/2017
helpviewer_keywords:
- application domains, about
- common language runtime, application domains
- runtime, application domains
ms.assetid: c6d99815-e022-4d2c-9420-1d7ab5b9d504
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5ebd1de46eb2757098a369b58dd9a6c0009e5b95
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2019
ms.locfileid: "61674888"
---
# <a name="using-application-domains"></a><span data-ttu-id="46ce8-102">Verwenden von Anwendungsdomänen</span><span class="sxs-lookup"><span data-stu-id="46ce8-102">Using Application Domains</span></span>
<span data-ttu-id="46ce8-103">Anwendungsdomänen stellen eine Isolationseinheit für die Common Language Runtime (CLR) bereit.</span><span class="sxs-lookup"><span data-stu-id="46ce8-103">Application domains provide a unit of isolation for the common language runtime.</span></span> <span data-ttu-id="46ce8-104">Sie werden in einem Prozess erstellt und dort ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="46ce8-104">They are created and run inside a process.</span></span> <span data-ttu-id="46ce8-105">Anwendungsdomänen werden normalerweise von einem Runtimehost erstellt. Dabei handelt es sich um eine Anwendung, die dafür verantwortlich ist, die Runtime in einen Prozess zu laden und Benutzercode innerhalb einer Anwendungsdomäne auszuführen.</span><span class="sxs-lookup"><span data-stu-id="46ce8-105">Application domains are usually created by a runtime host, which is an application responsible for loading the runtime into a process and executing user code within an application domain.</span></span> <span data-ttu-id="46ce8-106">Der Runtimehost erstellt einen Prozess und eine Standardanwendungsdomäne und führt darin verwalteten Code aus.</span><span class="sxs-lookup"><span data-stu-id="46ce8-106">The runtime host creates a process and a default application domain, and runs managed code inside it.</span></span> <span data-ttu-id="46ce8-107">Runtimehosts sind z.B. ASP.NET, Microsoft Internet Explorer und Windows-Shell.</span><span class="sxs-lookup"><span data-stu-id="46ce8-107">Runtime hosts include ASP.NET, Microsoft Internet Explorer, and the Windows shell.</span></span>  
  
 <span data-ttu-id="46ce8-108">Für die meisten Anwendungen müssen Sie nicht Ihre eigene Anwendungsdomäne erstellen. Der Runtimehost erstellt alle erforderlichen Anwendungsdomänen für Sie.</span><span class="sxs-lookup"><span data-stu-id="46ce8-108">For most applications, you do not need to create your own application domain; the runtime host creates any necessary application domains for you.</span></span> <span data-ttu-id="46ce8-109">Sie können aber zusätzliche Anwendungsdomänen erstellen und konfigurieren, wenn Ihre Anwendung Code isolieren oder DLLs verwenden und entladen muss.</span><span class="sxs-lookup"><span data-stu-id="46ce8-109">However, you can create and configure additional application domains if your application needs to isolate code or to use and unload DLLs.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="46ce8-110">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="46ce8-110">In This Section</span></span>  
 [<span data-ttu-id="46ce8-111">Vorgehensweise: Erstellen einer Anwendungsdomäne</span><span class="sxs-lookup"><span data-stu-id="46ce8-111">How to: Create an Application Domain</span></span>](../../../docs/framework/app-domains/how-to-create-an-application-domain.md)  
 <span data-ttu-id="46ce8-112">Erläutert, wie Sie eine Anwendungsdomäne programmgesteuert erstellen</span><span class="sxs-lookup"><span data-stu-id="46ce8-112">Describes how to programmatically create an application domain.</span></span>  
  
 [<span data-ttu-id="46ce8-113">Vorgehensweise: Entladen einer Anwendungsdomäne</span><span class="sxs-lookup"><span data-stu-id="46ce8-113">How to: Unload an Application Domain</span></span>](../../../docs/framework/app-domains/how-to-unload-an-application-domain.md)  
 <span data-ttu-id="46ce8-114">Erläutert, wie Sie eine Anwendungsdomäne programmgesteuert entladen</span><span class="sxs-lookup"><span data-stu-id="46ce8-114">Describes how to programmatically unload an application domain.</span></span>  
  
 [<span data-ttu-id="46ce8-115">Vorgehensweise: Konfigurieren einer Anwendungsdomäne</span><span class="sxs-lookup"><span data-stu-id="46ce8-115">How to: Configure an Application Domain</span></span>](../../../docs/framework/app-domains/how-to-configure-an-application-domain.md)  
 <span data-ttu-id="46ce8-116">Führt Sie in die Konfiguration einer Anwendungsdomäne ein</span><span class="sxs-lookup"><span data-stu-id="46ce8-116">Provides an introduction to configuring an application domain.</span></span>  
  
 [<span data-ttu-id="46ce8-117">Abrufen von Setupinformationen aus einer Anwendungsdomäne</span><span class="sxs-lookup"><span data-stu-id="46ce8-117">Retrieving Setup Information from an Application Domain</span></span>](../../../docs/framework/app-domains/retrieve-setup-information.md)  
 <span data-ttu-id="46ce8-118">Erläutert, wie Sie Setupinformationen aus einer Anwendungsdomäne abrufen können</span><span class="sxs-lookup"><span data-stu-id="46ce8-118">Describes how to retrieve setup information from an application domain.</span></span>  
  
 [<span data-ttu-id="46ce8-119">Vorgehensweise: Laden von Assemblys in eine Anwendungsdomäne</span><span class="sxs-lookup"><span data-stu-id="46ce8-119">How to: Load Assemblies into an Application Domain</span></span>](../../../docs/framework/app-domains/how-to-load-assemblies-into-an-application-domain.md)  
 <span data-ttu-id="46ce8-120">Erläutert wie Sie eine Assembly in eine Anwendungsdomäne laden können</span><span class="sxs-lookup"><span data-stu-id="46ce8-120">Describes how to load an assembly into an application domain.</span></span>  
  
 [<span data-ttu-id="46ce8-121">Vorgehensweise: Abrufen von Typ- und Memberinformationen aus einer Assembly</span><span class="sxs-lookup"><span data-stu-id="46ce8-121">How to: Obtain Type and Member Information from an Assembly</span></span>](../../../docs/framework/app-domains/how-to-obtain-type-and-member-information-from-an-assembly.md)  
 <span data-ttu-id="46ce8-122">Erläutert, wie Sie Informationen zu einer Assembly abrufen können</span><span class="sxs-lookup"><span data-stu-id="46ce8-122">Describes how to retrieve information about an assembly.</span></span>  
  
 [<span data-ttu-id="46ce8-123">Erstellen von Schattenkopien von Assemblys</span><span class="sxs-lookup"><span data-stu-id="46ce8-123">Shadow Copying Assemblies</span></span>](../../../docs/framework/app-domains/shadow-copy-assemblies.md)  
 <span data-ttu-id="46ce8-124">Erläutert, wie Sie Assemblys mit Schattenkopien aktualisieren können, während diese gerade verwendet werden, und wie Sie Schattenkopien konfigurieren können</span><span class="sxs-lookup"><span data-stu-id="46ce8-124">Describes how shadow copying allows updates to assemblies while they are in use, and how to configure shadow copying.</span></span>  
  
 [<span data-ttu-id="46ce8-125">Vorgehensweise: Empfangen von Ausnahmebenachrichtigungen (erste Chance)</span><span class="sxs-lookup"><span data-stu-id="46ce8-125">How to: Receive First-Chance Exception Notifications</span></span>](../../../docs/framework/app-domains/how-to-receive-first-chance-exception-notifications.md)  
 <span data-ttu-id="46ce8-126">Erläutert, wie Sie eine Benachrichtigung bezüglich einer ausgelösten Ausnahme abrufen können, bevor die CLR mit dem Suchen nach Ausnahmehandlern beginnt.</span><span class="sxs-lookup"><span data-stu-id="46ce8-126">Explains how you can receive a notification that an exception has been thrown, before the common language runtime has begun searching for exception handlers.</span></span>  
  
 [<span data-ttu-id="46ce8-127">Auflösen beim Laden von Assemblys</span><span class="sxs-lookup"><span data-stu-id="46ce8-127">Resolving Assembly Loads</span></span>](../../../docs/framework/app-domains/resolve-assembly-loads.md)  
 <span data-ttu-id="46ce8-128">Führt Sie in das Verwenden des Ereignisses <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> ein, um fehlgeschlagene Assemblyladevorgänge aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="46ce8-128">Provides guidance on using the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event to resolve assembly load failures.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="46ce8-129">Referenz</span><span class="sxs-lookup"><span data-stu-id="46ce8-129">Reference</span></span>  
 <xref:System.AppDomain>  
 <span data-ttu-id="46ce8-130">Stellt eine Anwendungsdomäne dar</span><span class="sxs-lookup"><span data-stu-id="46ce8-130">Represents an application domain.</span></span> <span data-ttu-id="46ce8-131">Bietet Methoden zum Erstellen und Steuern von Anwendungsdomänen</span><span class="sxs-lookup"><span data-stu-id="46ce8-131">Provides methods for creating and controlling application domains.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="46ce8-132">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="46ce8-132">Related Sections</span></span>  
 [<span data-ttu-id="46ce8-133">Assemblys in der Common Language Runtime (CLR)</span><span class="sxs-lookup"><span data-stu-id="46ce8-133">Assemblies in the Common Language Runtime</span></span>](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)  
 <span data-ttu-id="46ce8-134">Gibt einen Überblick über von Assemblys ausgeführte Funktionen</span><span class="sxs-lookup"><span data-stu-id="46ce8-134">Provides an overview of the functions performed by assemblies.</span></span>  
  
 [<span data-ttu-id="46ce8-135">Programmieren mit Assemblys</span><span class="sxs-lookup"><span data-stu-id="46ce8-135">Programming with Assemblies</span></span>](../../../docs/framework/app-domains/programming-with-assemblies.md)  
 <span data-ttu-id="46ce8-136">Beschreibt das Erstellen, Signieren und Festlegen von Attributen für Assemblys.</span><span class="sxs-lookup"><span data-stu-id="46ce8-136">Describes how to create, sign, and set attributes on assemblies.</span></span>  
  
 [<span data-ttu-id="46ce8-137">Ausgeben von dynamischen Methoden und Assemblys</span><span class="sxs-lookup"><span data-stu-id="46ce8-137">Emitting Dynamic Methods and Assemblies</span></span>](../../../docs/framework/reflection-and-codedom/emitting-dynamic-methods-and-assemblies.md)  
 <span data-ttu-id="46ce8-138">Beschreibt das Erstellen dynamischer Assemblys.</span><span class="sxs-lookup"><span data-stu-id="46ce8-138">Describes how to create dynamic assemblies.</span></span>  
  
 [<span data-ttu-id="46ce8-139">Anwendungsdomänen</span><span class="sxs-lookup"><span data-stu-id="46ce8-139">Application Domains</span></span>](../../../docs/framework/app-domains/application-domains.md)  
 <span data-ttu-id="46ce8-140">Bietet eine konzeptionelle Übersicht über Anwendungsdomänen.</span><span class="sxs-lookup"><span data-stu-id="46ce8-140">Provides a conceptual overview of application domains.</span></span>  
  
 [<span data-ttu-id="46ce8-141">Übersicht über Reflektion</span><span class="sxs-lookup"><span data-stu-id="46ce8-141">Reflection Overview</span></span>](../../../docs/framework/reflection-and-codedom/reflection.md)  
 <span data-ttu-id="46ce8-142">Beschreibt, wie die **Reflektion**-Klasse verwendet wird, um Informationen zu einer Assembly abzurufen.</span><span class="sxs-lookup"><span data-stu-id="46ce8-142">Describes how to use the **Reflection** class to obtain information about an assembly.</span></span>

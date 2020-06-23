---
title: Programmieren mit Anwendungsdomänen und Assemblys
description: Lernen Sie das Programmieren mit Anwendungsdomänen und Assemblys in .NET kennen. Weitere Informationen finden Sie über Links zu Themen zu Vorgehensweisen und Beispielen zum Erstellen von Anwendungsdomänen und Assemblys.
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], programming
- programming assemblies
- application domains, programming
- programming application domains
ms.assetid: 96d3b8e3-bef8-4da0-9a81-9841e23a94e9
ms.openlocfilehash: 1c28fe0abeb279a1dbbc6dcf043c1780c72d79df
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2020
ms.locfileid: "84903437"
---
# <a name="programming-with-application-domains-and-assemblies"></a><span data-ttu-id="15c25-104">Programmieren mit Anwendungsdomänen und Assemblys</span><span class="sxs-lookup"><span data-stu-id="15c25-104">Programming with Application Domains and Assemblies</span></span>

<span data-ttu-id="15c25-105">Hosts wie z.B. Microsoft Internet Explorer, ASP.NET und Windows-Shell laden die Common Language Runtime in einen Prozess, erstellen eine [Anwendungsdomäne](application-domains.md) in diesem Prozess und laden dann Benutzercode in diese Anwendungsdomäne und führen ihn aus, wenn eine .NET Framework-Anwendung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="15c25-105">Hosts such as Microsoft Internet Explorer, ASP.NET, and the Windows shell load the common language runtime into a process, create an [application domain](application-domains.md) in that process, and then load and execute user code in that application domain when running a .NET Framework application.</span></span> <span data-ttu-id="15c25-106">In den meisten Fällen müssen Sie sich nicht darum kümmern, Anwendungsdomänen zu erstellen und Assemblys hinein zu laden, da der Laufzeithost diese Aufgaben ausführt.</span><span class="sxs-lookup"><span data-stu-id="15c25-106">In most cases, you do not have to worry about creating application domains and loading assemblies into them because the runtime host performs those tasks.</span></span>  
  
<span data-ttu-id="15c25-107">Wenn Sie jedoch eine Anwendung erstellen, die die Common Language Runtime hostet, Tools oder Code erstellen, den Sie programmgesteuert entladen möchten, oder austauschbare Komponenten erstellen, die spontan entladen und neu geladen werden können, erstellen Sie Ihre eigenen Anwendungsdomänen.</span><span class="sxs-lookup"><span data-stu-id="15c25-107">However, if you are creating an application that will host the common language runtime, creating tools or code you want to unload programmatically, or creating pluggable components that can be unloaded and reloaded on the fly, you will be creating your own application domains.</span></span> <span data-ttu-id="15c25-108">Auch wenn Sie keinen Laufzeithost erstellen, können Sie diesem Abschnitt wichtige Informationen entnehmen zum Arbeiten mit Anwendungsdomänen und Assemblys, die in diese Anwendungsdomänen geladen werden.</span><span class="sxs-lookup"><span data-stu-id="15c25-108">Even if you are not creating a runtime host, this section provides important information on how to work with application domains and assemblies loaded in these application domains.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="15c25-109">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="15c25-109">In This Section</span></span>  

[<span data-ttu-id="15c25-110">Gewusst-wie-Themen zu Anwendungsdomänen und Assemblys</span><span class="sxs-lookup"><span data-stu-id="15c25-110">Application Domains and Assemblies How-to Topics</span></span>](application-domains-and-assemblies-how-to-topics.md)  
<span data-ttu-id="15c25-111">Enthält Links zu allen Gewusst-wie-Themen in der Begriffsdokumentation zum Programmieren mit Anwendungsdomänen und Assemblys.</span><span class="sxs-lookup"><span data-stu-id="15c25-111">Provides links to all How-to topics found in the conceptual documentation for programming with application domains and assemblies.</span></span>  
  
[<span data-ttu-id="15c25-112">Verwenden von Anwendungsdomänen</span><span class="sxs-lookup"><span data-stu-id="15c25-112">Using Application Domains</span></span>](use.md)  
<span data-ttu-id="15c25-113">Stellt Beispiele zum Erstellen, Konfigurieren und Verwenden von Anwendungsdomänen bereit.</span><span class="sxs-lookup"><span data-stu-id="15c25-113">Provides examples of creating, configuring, and using application domains.</span></span>  
  
[<span data-ttu-id="15c25-114">Programmieren mit Assemblys</span><span class="sxs-lookup"><span data-stu-id="15c25-114">Programming with Assemblies</span></span>](../../standard/assembly/index.md)  
<span data-ttu-id="15c25-115">Beschreibt das Erstellen, Signieren und Festlegen von Attributen für Assemblys.</span><span class="sxs-lookup"><span data-stu-id="15c25-115">Describes how to create, sign, and set attributes on assemblies.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="15c25-116">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="15c25-116">Related Sections</span></span>  

[<span data-ttu-id="15c25-117">Ausgeben von dynamischen Methoden und Assemblys</span><span class="sxs-lookup"><span data-stu-id="15c25-117">Emitting Dynamic Methods and Assemblies</span></span>](../reflection-and-codedom/emitting-dynamic-methods-and-assemblies.md)  
<span data-ttu-id="15c25-118">Beschreibt das Erstellen dynamischer Assemblys.</span><span class="sxs-lookup"><span data-stu-id="15c25-118">Describes how to create dynamic assemblies.</span></span>  
  
[<span data-ttu-id="15c25-119">Assemblys in .NET</span><span class="sxs-lookup"><span data-stu-id="15c25-119">Assemblies in .NET</span></span>](../../standard/assembly/index.md)  
<span data-ttu-id="15c25-120">Bietet eine konzeptionelle Übersicht über Assemblys.</span><span class="sxs-lookup"><span data-stu-id="15c25-120">Provides a conceptual overview of assemblies.</span></span>  
  
[<span data-ttu-id="15c25-121">Anwendungsdomänen</span><span class="sxs-lookup"><span data-stu-id="15c25-121">Application Domains</span></span>](application-domains.md)  
<span data-ttu-id="15c25-122">Bietet eine konzeptionelle Übersicht über Anwendungsdomänen.</span><span class="sxs-lookup"><span data-stu-id="15c25-122">Provides a conceptual overview of application domains.</span></span>  
  
[<span data-ttu-id="15c25-123">Übersicht über Reflektion</span><span class="sxs-lookup"><span data-stu-id="15c25-123">Reflection Overview</span></span>](../reflection-and-codedom/reflection.md)  
<span data-ttu-id="15c25-124">Beschreibt, wie die **Reflektion**-Klasse verwendet wird, um Informationen zu einer Assembly abzurufen.</span><span class="sxs-lookup"><span data-stu-id="15c25-124">Describes how to use the **Reflection** class to obtain information about an assembly.</span></span>

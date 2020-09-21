---
title: Verfügbarmachen von .NET-Komponenten im COM
description: Machen Sie .NET-Komponenten in COM verfügbar. Qualifizieren Sie .NET-Typen für die Interoperation. Wenden Sie Interop-Attribute an. Packen Sie eine Assembly für COM. Nutzen Sie einen verwalteten Typ aus COM.
ms.date: 03/30/2017
helpviewer_keywords:
- exposing .NET Framework components to COM
- interoperation with unmanaged code, exposing .NET Framework components
- COM interop, exposing COM components
ms.assetid: e42a65f7-1e61-411f-b09a-aca1bbce24c6
ms.openlocfilehash: dc808f3e8d6bd89ba979d43e5b4ec9d787bd09b1
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90545258"
---
# <a name="exposing-net-components-to-com"></a><span data-ttu-id="c2ebc-107">Verfügbarmachen von .NET-Komponenten im COM</span><span class="sxs-lookup"><span data-stu-id="c2ebc-107">Exposing .NET components to COM</span></span>

<span data-ttu-id="c2ebc-108">Das Schreiben eines .NET-Typs und das Verwenden dieses Typs von nicht verwaltetem Code sind unterschiedliche Aktivitäten für Entwickler.</span><span class="sxs-lookup"><span data-stu-id="c2ebc-108">Writing a .NET type and consuming that type from unmanaged code are distinct activities for developers.</span></span> <span data-ttu-id="c2ebc-109">Dieser Abschnitt beschreibt einige Tipps zum Schreiben von verwaltetem Code, der mit COM-Clients interagiert:</span><span class="sxs-lookup"><span data-stu-id="c2ebc-109">This section describes several tips for writing managed code that interoperates with COM clients:</span></span>

- <span data-ttu-id="c2ebc-110">[Qualifizieren von .NET-Typen für die Interoperation](../../standard/native-interop/qualify-net-types-for-interoperation.md).</span><span class="sxs-lookup"><span data-stu-id="c2ebc-110">[Qualifying .NET types for interoperation](../../standard/native-interop/qualify-net-types-for-interoperation.md).</span></span>

     <span data-ttu-id="c2ebc-111">Alle verwalteten Typen, Methoden, Eigenschaften, Felder und Ereignisse, die für COM verfügbar gemacht werden sollen, müssen öffentlich sein.</span><span class="sxs-lookup"><span data-stu-id="c2ebc-111">All managed types, methods, properties, fields, and events that you want to expose to COM must be public.</span></span> <span data-ttu-id="c2ebc-112">Typen müssen über einen öffentlichen parameterlosen Konstruktor verfügen, da dies der einzige Konstruktor ist, der über COM aufgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="c2ebc-112">Types must have a public parameterless constructor, which is the only constructor that can be invoked through COM.</span></span>

- <span data-ttu-id="c2ebc-113">[Anwenden von Interop-Attributen](../../standard/native-interop/apply-interop-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="c2ebc-113">[Applying interop attributes](../../standard/native-interop/apply-interop-attributes.md).</span></span>

     <span data-ttu-id="c2ebc-114">Benutzerdefinierte Attribute in verwaltetem Code können die Interoperabilität einer Komponente verbessern.</span><span class="sxs-lookup"><span data-stu-id="c2ebc-114">Custom attributes within managed code can enhance the interoperability of a component.</span></span>

- <span data-ttu-id="c2ebc-115">[Packen einer Assembly für COM](packaging-an-assembly-for-com.md).</span><span class="sxs-lookup"><span data-stu-id="c2ebc-115">[Packaging an assembly for COM](packaging-an-assembly-for-com.md).</span></span>

     <span data-ttu-id="c2ebc-116">COM-Entwickler fordern möglicherweise, dass Sie die Schritte für Verweise und die Bereitstellung Ihrer Assemblys zusammenfassen.</span><span class="sxs-lookup"><span data-stu-id="c2ebc-116">COM developers might require that you summarize the steps involved in referencing and deploying your assemblies.</span></span>

 <span data-ttu-id="c2ebc-117">Darüber hinaus werden in diesem Abschnitt die Aufgaben im Zusammenhang mit der Nutzung eines verwalteten Typs von einem COM-Client beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c2ebc-117">Additionally, this section identifies the tasks related to consuming a managed type from a COM client.</span></span>

## <a name="to-consume-a-managed-type-from-com"></a><span data-ttu-id="c2ebc-118">Nutzen eines verwalteten Typs von COM</span><span class="sxs-lookup"><span data-stu-id="c2ebc-118">To consume a managed type from COM</span></span>

1. <span data-ttu-id="c2ebc-119">[Registrieren von Assemblys bei COM](registering-assemblies-with-com.md).</span><span class="sxs-lookup"><span data-stu-id="c2ebc-119">[Register assemblies with COM](registering-assemblies-with-com.md).</span></span>

     <span data-ttu-id="c2ebc-120">Typen in einer Assembly (und Typbibliotheken) müssen zur Entwurfszeit registriert werden.</span><span class="sxs-lookup"><span data-stu-id="c2ebc-120">Types in an assembly (and type libraries) must be registered at design time.</span></span> <span data-ttu-id="c2ebc-121">Wenn ein Installer die Assembly nicht registriert, weisen Sie die COM-Entwickler zur Nutzung von Regasm.exe an.</span><span class="sxs-lookup"><span data-stu-id="c2ebc-121">If an installer does not register the assembly, instruct COM developers to use Regasm.exe.</span></span>

2. <span data-ttu-id="c2ebc-122">[Verweisen auf .NET-Typen in COM](how-to-reference-net-types-from-com.md).</span><span class="sxs-lookup"><span data-stu-id="c2ebc-122">[Reference .NET types from COM](how-to-reference-net-types-from-com.md).</span></span>

     <span data-ttu-id="c2ebc-123">COM-Entwickler können auf Typen in einer Assembly verweisen, indem sie dieselben Tools und Techniken nutzen, die sie heute bereits verwenden.</span><span class="sxs-lookup"><span data-stu-id="c2ebc-123">COM developers can reference types in an assembly using the same tools and techniques they use today.</span></span>

3. <span data-ttu-id="c2ebc-124">[Aufrufen eines .NET-Objekts](/previous-versions/dotnet/netframework-4.0/8hw8h46b(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="c2ebc-124">[Call a .NET object](/previous-versions/dotnet/netframework-4.0/8hw8h46b(v=vs.100)).</span></span>

     <span data-ttu-id="c2ebc-125">COM-Entwickler können Methoden so für das .NET-Objekt aufrufen, wie sie Methoden für alle nicht verwalteten Typen aufrufen.</span><span class="sxs-lookup"><span data-stu-id="c2ebc-125">COM developers can call methods on the .NET object the same way they call methods on any unmanaged type.</span></span> <span data-ttu-id="c2ebc-126">Z.B. aktiviert die COM-API **CoCreateInstance** .NET-Objekte.</span><span class="sxs-lookup"><span data-stu-id="c2ebc-126">For example, the COM **CoCreateInstance** API activates .NET objects.</span></span>

4. <span data-ttu-id="c2ebc-127">[Bereitstellen einer Anwendung für COM-Zugriff](/previous-versions/dotnet/netframework-4.0/c2850st8(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="c2ebc-127">[Deploy an application for COM access](/previous-versions/dotnet/netframework-4.0/c2850st8(v=vs.100)).</span></span>

     <span data-ttu-id="c2ebc-128">Eine Assembly mit starkem Namen kann im globalen Assemblycache installiert werden und erfordert eine Signatur des Herausgebers.</span><span class="sxs-lookup"><span data-stu-id="c2ebc-128">A strong-named assembly can be installed in the global assembly cache and requires a signature from its publisher.</span></span> <span data-ttu-id="c2ebc-129">Assemblys, die keinen starken Namen haben, müssen im Anwendungsverzeichnis des Clients installiert werden.</span><span class="sxs-lookup"><span data-stu-id="c2ebc-129">Assemblies that are not strong named must be installed in the application directory of the client.</span></span>

## <a name="see-also"></a><span data-ttu-id="c2ebc-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c2ebc-130">See also</span></span>

- [<span data-ttu-id="c2ebc-131">Interoperabilität mit nicht verwaltetem Code</span><span class="sxs-lookup"><span data-stu-id="c2ebc-131">Interoperating with Unmanaged Code</span></span>](index.md)
- [<span data-ttu-id="c2ebc-132">COM-Interopbeispiel: COM-Client und .NET-Server</span><span class="sxs-lookup"><span data-stu-id="c2ebc-132">COM Interop Sample: COM Client and .NET Server</span></span>](com-interop-sample-com-client-and-net-server.md)

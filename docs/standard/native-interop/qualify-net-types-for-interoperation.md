---
title: Qualifizieren von .NET-Typen für die COM-Interoperation
description: Dieser Artikel enthält Richtlinien, die Ihnen helfen, Typen in einer .NET-Assembly für COM-Anwendungen für COM-Interop verfügbar zu machen.
ms.date: 03/30/2017
helpviewer_keywords:
- exposing .NET components to COM
- COM interop, qualifying .NET types
- qualifying .NET types for interoperation
- interoperation with unmanaged code, qualifying .NET types
- interoperation with unmanaged code, exposing .NET components
- COM interop, exposing COM components
ms.assetid: 4b8afb52-fb8d-4e65-b47c-fd82956a3cdd
ms.openlocfilehash: 3fa9f0d5d8dd4d532fc510a1d946eddf32016748
ms.sourcegitcommit: 7588b1f16b7608bc6833c05f91ae670c22ef56f8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/02/2020
ms.locfileid: "93187761"
---
# <a name="qualifying-net-types-for-com-interoperation"></a><span data-ttu-id="d2762-103">Qualifizieren von .NET-Typen für die COM-Interoperation</span><span class="sxs-lookup"><span data-stu-id="d2762-103">Qualifying .NET Types for COM Interoperation</span></span>
<span data-ttu-id="d2762-104">Wenn Sie beabsichtigen, Typen in einer Assembly für eine COM-Anwendung verfügbar zu machen, beachten Sie zur Entwurfszeit die Anforderungen von Com-Interop.</span><span class="sxs-lookup"><span data-stu-id="d2762-104">If you intend to expose types in an assembly to COM applications, consider the requirements of COM interop at design time.</span></span> <span data-ttu-id="d2762-105">Verwaltete Typen (Klassen, Schnittstellen, Strukturen und Enumerationen) lassen sich nahtlos in COM-Typen integrieren, wenn Sie die folgenden Richtlinien einhalten:</span><span class="sxs-lookup"><span data-stu-id="d2762-105">Managed types (class, interface, structure, and enumeration) seamlessly integrate with COM types when you adhere to the following guidelines:</span></span>  
  
- <span data-ttu-id="d2762-106">Klassen sollten Schnittstellen explizit implementieren.</span><span class="sxs-lookup"><span data-stu-id="d2762-106">Classes should implement interfaces explicitly.</span></span>  
  
     <span data-ttu-id="d2762-107">COM-Interop stellt zwar einen Mechanismus bereit, mit dem automatisch eine Schnittstelle generiert wird, die alle Member einer Klasse und die Member der dazugehörigen Basisklasse enthält, dennoch ist es besser, explizite Schnittstellen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="d2762-107">Although COM interop provides a mechanism to automatically generate an interface containing all members of the class and the members of its base class, it is far better to provide explicit interfaces.</span></span> <span data-ttu-id="d2762-108">Die automatisch generierte Schnittstelle wird als Klassenschnittstelle bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="d2762-108">The automatically generated interface is called the class interface.</span></span> <span data-ttu-id="d2762-109">Informationen zu Richtlinien finden Sie unter [Einführung in die Klassenschnittstelle](com-callable-wrapper.md#introducing-the-class-interface).</span><span class="sxs-lookup"><span data-stu-id="d2762-109">For guidelines, see [Introducing the class interface](com-callable-wrapper.md#introducing-the-class-interface).</span></span>  
  
     <span data-ttu-id="d2762-110">Sie können Visual Basic, C# und C++ verwenden, um Schnittstellendefinitionen in Ihren Code einzuschließen. So müssen Sie nicht die Interface Definition Language (IDL) oder eine ähnliche Sprache verwenden.</span><span class="sxs-lookup"><span data-stu-id="d2762-110">You can use Visual Basic, C#, and C++ to incorporate interface definitions in your code, instead of having to use Interface Definition Language (IDL) or its equivalent.</span></span> <span data-ttu-id="d2762-111">Einzelheiten zur Syntax finden Sie in der Dokumentation zur Sprache.</span><span class="sxs-lookup"><span data-stu-id="d2762-111">For syntax details, see your language documentation.</span></span>  
  
- <span data-ttu-id="d2762-112">Verwaltete Typen müssen öffentlich sein.</span><span class="sxs-lookup"><span data-stu-id="d2762-112">Managed types must be public.</span></span>  
  
     <span data-ttu-id="d2762-113">Nur öffentliche Typen in einer Assembly werden registriert und in die Typbibliothek exportiert.</span><span class="sxs-lookup"><span data-stu-id="d2762-113">Only public types in an assembly are registered and exported to the type library.</span></span> <span data-ttu-id="d2762-114">Dies hat zur Folge, dass nur öffentliche Typen für das COM sichtbar sind.</span><span class="sxs-lookup"><span data-stu-id="d2762-114">As a result, only public types are visible to COM.</span></span>  
  
     <span data-ttu-id="d2762-115">Dank verwalteter Typen stehen Funktionen auch in anderem verwaltetem Code zur Verfügung, der möglicherweise nicht für COM verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="d2762-115">Managed types expose features to other managed code that might not be exposed to COM.</span></span> <span data-ttu-id="d2762-116">COM-Clients haben z.B. keinen Zugriff auf parametrisierte Konstruktoren, statische Methoden und Konstantenfelder.</span><span class="sxs-lookup"><span data-stu-id="d2762-116">For instance, parameterized constructors, static methods, and constant fields are not exposed to COM clients.</span></span> <span data-ttu-id="d2762-117">Wenn die Runtime Daten in einen Typ hinein und aus einem Typ heraus marshallt, werden diese Daten möglicherweise kopiert oder umgewandelt.</span><span class="sxs-lookup"><span data-stu-id="d2762-117">Further, as the runtime marshals data in and out of a type, the data might be copied or transformed.</span></span>  
  
- <span data-ttu-id="d2762-118">Methoden, Eigenschaften, Felder und Ereignisse müssen öffentlich sein.</span><span class="sxs-lookup"><span data-stu-id="d2762-118">Methods, properties, fields, and events must be public.</span></span>  
  
     <span data-ttu-id="d2762-119">Member öffentlicher Typen müssen ebenfalls öffentlich sein, wenn sie im COM sichtbar sein sollen.</span><span class="sxs-lookup"><span data-stu-id="d2762-119">Members of public types must also be public if they are to be visible to COM.</span></span> <span data-ttu-id="d2762-120">Sie können die Sichtbarkeit einer Assembly, eines öffentlichen Typs oder öffentlicher Member eines öffentlichen Typs einschränken, indem Sie die Klasse <xref:System.Runtime.InteropServices.ComVisibleAttribute> anwenden.</span><span class="sxs-lookup"><span data-stu-id="d2762-120">You can restrict the visibility of an assembly, a public type, or public members of a public type by applying the <xref:System.Runtime.InteropServices.ComVisibleAttribute>.</span></span> <span data-ttu-id="d2762-121">Standardmäßig sind alle öffentlichen Typen und Member sichtbar.</span><span class="sxs-lookup"><span data-stu-id="d2762-121">By default, all public types and members are visible.</span></span>  
  
- <span data-ttu-id="d2762-122">Typen müssen über einen öffentlichen parameterlosen Konstruktor verfügen, um über COM aktiviert werden zu können.</span><span class="sxs-lookup"><span data-stu-id="d2762-122">Types must have a public parameterless constructor to be activated from COM.</span></span>  
  
     <span data-ttu-id="d2762-123">Verwaltete, öffentliche Typen sind im COM sichtbar.</span><span class="sxs-lookup"><span data-stu-id="d2762-123">Managed, public types are visible to COM.</span></span> <span data-ttu-id="d2762-124">Ohne öffentlichen parameterlosen Konstruktor (Konstruktor ohne Argumente) können COM-Clients den Typ nicht erstellen.</span><span class="sxs-lookup"><span data-stu-id="d2762-124">However, without a public parameterless constructor (a constructor with no arguments), COM clients cannot create the type.</span></span> <span data-ttu-id="d2762-125">Wenn er auf andere Art und Weise aktiviert wird, können sie den Typ aber dennoch verwenden.</span><span class="sxs-lookup"><span data-stu-id="d2762-125">COM clients can still use the type if it is activated by some other means.</span></span>  
  
- <span data-ttu-id="d2762-126">Typen können nicht abstrakt sein.</span><span class="sxs-lookup"><span data-stu-id="d2762-126">Types cannot be abstract.</span></span>  
  
     <span data-ttu-id="d2762-127">Weder COM-Clients noch .NET-Clients können abstrakte Typen erstellen.</span><span class="sxs-lookup"><span data-stu-id="d2762-127">Neither COM clients nor .NET clients can create abstract types.</span></span>  
  
 <span data-ttu-id="d2762-128">Beim Export eines verwalteten Typs in das COM wird seine Vererbungshierarchie vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="d2762-128">When exported to COM, the inheritance hierarchy of a managed type is flattened.</span></span> <span data-ttu-id="d2762-129">Auch die Versionsverwaltung läuft bei verwalteten und nicht verwalteten Umgebungen unterschiedlich ab.</span><span class="sxs-lookup"><span data-stu-id="d2762-129">Versioning also differs between managed and unmanaged environments.</span></span> <span data-ttu-id="d2762-130">Im COM verfügbare Typen haben nicht dieselben Versionsverwaltungseigenschaften wie andere verwaltete Typen.</span><span class="sxs-lookup"><span data-stu-id="d2762-130">Types exposed to COM do not have the same versioning characteristics as other managed types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2762-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d2762-131">See also</span></span>

- <xref:System.Runtime.InteropServices.ComVisibleAttribute>
- [<span data-ttu-id="d2762-132">Verfügbarmachen von .NET Framework-Komponenten in COM</span><span class="sxs-lookup"><span data-stu-id="d2762-132">Exposing .NET Framework Components to COM</span></span>](../../framework/interop/exposing-dotnet-components-to-com.md)
- [<span data-ttu-id="d2762-133">Einführung in die Klassenschnittstelle</span><span class="sxs-lookup"><span data-stu-id="d2762-133">Introducing the class interface</span></span>](com-callable-wrapper.md#introducing-the-class-interface)
- [<span data-ttu-id="d2762-134">Anwenden von Interop-Attributen</span><span class="sxs-lookup"><span data-stu-id="d2762-134">Applying Interop Attributes</span></span>](apply-interop-attributes.md)
- [<span data-ttu-id="d2762-135">Verpacken einer .NET Framework-Assembly für COM</span><span class="sxs-lookup"><span data-stu-id="d2762-135">Packaging a .NET Framework Assembly for COM</span></span>](../../framework/interop/packaging-an-assembly-for-com.md)

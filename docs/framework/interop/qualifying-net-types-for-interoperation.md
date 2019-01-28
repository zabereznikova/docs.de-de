---
title: Qualifizieren von .NET-Typen für die Interoperation
ms.date: 03/30/2017
helpviewer_keywords:
- exposing .NET Framework components to COM
- COM interop, qualifying .NET types
- qualifying .NET types for interoperation
- interoperation with unmanaged code, qualifying .NET types
- interoperation with unmanaged code, exposing .NET Framework components
- COM interop, exposing COM components
ms.assetid: 4b8afb52-fb8d-4e65-b47c-fd82956a3cdd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a40b9524990213eaaf2ed78503b6f831776306ec
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54524311"
---
# <a name="qualifying-net-types-for-interoperation"></a><span data-ttu-id="2c699-102">Qualifizieren von .NET-Typen für die Interoperation</span><span class="sxs-lookup"><span data-stu-id="2c699-102">Qualifying .NET Types for Interoperation</span></span>
<span data-ttu-id="2c699-103">Wenn Sie beabsichtigen, Typen in einer Assembly für eine COM-Anwendung verfügbar zu machen, beachten Sie zur Entwurfszeit die Anforderungen von Com-Interop.</span><span class="sxs-lookup"><span data-stu-id="2c699-103">If you intend to expose types in an assembly to COM applications, consider the requirements of COM interop at design time.</span></span> <span data-ttu-id="2c699-104">Verwaltete Typen (Klassen, Schnittstellen, Strukturen und Enumerationen) lassen sich nahtlos in COM-Typen integrieren, wenn Sie die folgenden Richtlinien einhalten:</span><span class="sxs-lookup"><span data-stu-id="2c699-104">Managed types (class, interface, structure, and enumeration) seamlessly integrate with COM types when you adhere to the following guidelines:</span></span>  
  
-   <span data-ttu-id="2c699-105">Klassen sollten Schnittstellen explizit implementieren.</span><span class="sxs-lookup"><span data-stu-id="2c699-105">Classes should implement interfaces explicitly.</span></span>  
  
     <span data-ttu-id="2c699-106">COM-Interop stellt zwar einen Mechanismus bereit, mit dem automatisch eine Schnittstelle generiert wird, die alle Member einer Klasse und die Member der dazugehörigen Basisklasse enthält, dennoch ist es besser, explizite Schnittstellen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="2c699-106">Although COM interop provides a mechanism to automatically generate an interface containing all members of the class and the members of its base class, it is far better to provide explicit interfaces.</span></span> <span data-ttu-id="2c699-107">Die automatisch generierte Schnittstelle wird als Klassenschnittstelle bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="2c699-107">The automatically generated interface is called the class interface.</span></span> <span data-ttu-id="2c699-108">Informationen zu Richtlinien finden Sie unter [Einführung in die Klassenschnittstelle](com-callable-wrapper.md#introducing-the-class-interface).</span><span class="sxs-lookup"><span data-stu-id="2c699-108">For guidelines, see [Introducing the class interface](com-callable-wrapper.md#introducing-the-class-interface).</span></span>  
  
     <span data-ttu-id="2c699-109">Sie können Visual Basic, C# und C++ verwenden, um Schnittstellendefinitionen in Ihren Code einzuschließen. So müssen Sie nicht die Interface Definition Language (IDL) oder eine ähnliche Sprache verwenden.</span><span class="sxs-lookup"><span data-stu-id="2c699-109">You can use Visual Basic, C#, and C++ to incorporate interface definitions in your code, instead of having to use Interface Definition Language (IDL) or its equivalent.</span></span> <span data-ttu-id="2c699-110">Einzelheiten zur Syntax finden Sie in der Dokumentation zur Sprache.</span><span class="sxs-lookup"><span data-stu-id="2c699-110">For syntax details, see your language documentation.</span></span>  
  
-   <span data-ttu-id="2c699-111">Verwaltete Typen müssen öffentlich sein.</span><span class="sxs-lookup"><span data-stu-id="2c699-111">Managed types must be public.</span></span>  
  
     <span data-ttu-id="2c699-112">Nur öffentliche Typen in einer Assembly werden registriert und in die Typbibliothek exportiert.</span><span class="sxs-lookup"><span data-stu-id="2c699-112">Only public types in an assembly are registered and exported to the type library.</span></span> <span data-ttu-id="2c699-113">Dies hat zur Folge, dass nur öffentliche Typen für das COM sichtbar sind.</span><span class="sxs-lookup"><span data-stu-id="2c699-113">As a result, only public types are visible to COM.</span></span>  
  
     <span data-ttu-id="2c699-114">Dank verwalteter Typen stehen Funktionen auch in anderem verwaltetem Code zur Verfügung, der möglicherweise nicht für COM verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="2c699-114">Managed types expose features to other managed code that might not be exposed to COM.</span></span> <span data-ttu-id="2c699-115">COM-Clients haben z.B. keinen Zugriff auf parametrisierte Konstruktoren, statische Methoden und Konstantenfelder.</span><span class="sxs-lookup"><span data-stu-id="2c699-115">For instance, parameterized constructors, static methods, and constant fields are not exposed to COM clients.</span></span> <span data-ttu-id="2c699-116">Wenn die Runtime Daten in einen Typ hinein und aus einem Typ heraus marshallt, werden diese Daten möglicherweise kopiert oder umgewandelt.</span><span class="sxs-lookup"><span data-stu-id="2c699-116">Further, as the runtime marshals data in and out of a type, the data might be copied or transformed.</span></span>  
  
-   <span data-ttu-id="2c699-117">Methoden, Eigenschaften, Felder und Ereignisse müssen öffentlich sein.</span><span class="sxs-lookup"><span data-stu-id="2c699-117">Methods, properties, fields, and events must be public.</span></span>  
  
     <span data-ttu-id="2c699-118">Member öffentlicher Typen müssen ebenfalls öffentlich sein, wenn sie im COM sichtbar sein sollen.</span><span class="sxs-lookup"><span data-stu-id="2c699-118">Members of public types must also be public if they are to be visible to COM.</span></span> <span data-ttu-id="2c699-119">Sie können die Sichtbarkeit einer Assembly, eines öffentlichen Typs oder öffentlicher Member eines öffentlichen Typs einschränken, indem Sie die Klasse <xref:System.Runtime.InteropServices.ComVisibleAttribute> anwenden.</span><span class="sxs-lookup"><span data-stu-id="2c699-119">You can restrict the visibility of an assembly, a public type, or public members of a public type by applying the <xref:System.Runtime.InteropServices.ComVisibleAttribute>.</span></span> <span data-ttu-id="2c699-120">Standardmäßig sind alle öffentlichen Typen und Member sichtbar.</span><span class="sxs-lookup"><span data-stu-id="2c699-120">By default, all public types and members are visible.</span></span>  
  
-   <span data-ttu-id="2c699-121">Typen müssen über einen öffentlichen Standardkonstruktor verfügen, der sich über das COM aktivieren lässt.</span><span class="sxs-lookup"><span data-stu-id="2c699-121">Types must have a public default constructor to be activated from COM.</span></span>  
  
     <span data-ttu-id="2c699-122">Verwaltete, öffentliche Typen sind im COM sichtbar.</span><span class="sxs-lookup"><span data-stu-id="2c699-122">Managed, public types are visible to COM.</span></span> <span data-ttu-id="2c699-123">Ohne einen öffentlichen Standardkonstruktor (d.h. einen Konstruktor ohne Argumente) können COM-Clients den Typ nicht erstellen.</span><span class="sxs-lookup"><span data-stu-id="2c699-123">However, without a public default constructor (a constructor with no arguments), COM clients cannot create the type.</span></span> <span data-ttu-id="2c699-124">Wenn er auf andere Art und Weise aktiviert wird, können sie den Typ aber dennoch verwenden.</span><span class="sxs-lookup"><span data-stu-id="2c699-124">COM clients can still use the type if it is activated by some other means.</span></span>  
  
-   <span data-ttu-id="2c699-125">Typen können nicht abstrakt sein.</span><span class="sxs-lookup"><span data-stu-id="2c699-125">Types cannot be abstract.</span></span>  
  
     <span data-ttu-id="2c699-126">Weder COM-Clients noch .NET-Clients können abstrakte Typen erstellen.</span><span class="sxs-lookup"><span data-stu-id="2c699-126">Neither COM clients nor .NET clients can create abstract types.</span></span>  
  
 <span data-ttu-id="2c699-127">Beim Export eines verwalteten Typs in das COM wird seine Vererbungshierarchie vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="2c699-127">When exported to COM, the inheritance hierarchy of a managed type is flattened.</span></span> <span data-ttu-id="2c699-128">Auch die Versionsverwaltung läuft bei verwalteten und nicht verwalteten Umgebungen unterschiedlich ab.</span><span class="sxs-lookup"><span data-stu-id="2c699-128">Versioning also differs between managed and unmanaged environments.</span></span> <span data-ttu-id="2c699-129">Im COM verfügbare Typen haben nicht dieselben Versionsverwaltungseigenschaften wie andere verwaltete Typen.</span><span class="sxs-lookup"><span data-stu-id="2c699-129">Types exposed to COM do not have the same versioning characteristics as other managed types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c699-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2c699-130">See also</span></span>
- <xref:System.Runtime.InteropServices.ComVisibleAttribute>
- [<span data-ttu-id="2c699-131">Verfügbarmachen von .NET Framework-Komponenten in COM</span><span class="sxs-lookup"><span data-stu-id="2c699-131">Exposing .NET Framework Components to COM</span></span>](../../../docs/framework/interop/exposing-dotnet-components-to-com.md)
- [<span data-ttu-id="2c699-132">Einführung in die Klassenschnittstelle</span><span class="sxs-lookup"><span data-stu-id="2c699-132">Introducing the class interface</span></span>](com-callable-wrapper.md#introducing-the-class-interface)
- [<span data-ttu-id="2c699-133">Anwenden von Interop-Attributen</span><span class="sxs-lookup"><span data-stu-id="2c699-133">Applying Interop Attributes</span></span>](../../../docs/framework/interop/applying-interop-attributes.md)
- [<span data-ttu-id="2c699-134">Verpacken einer Assembly für COM</span><span class="sxs-lookup"><span data-stu-id="2c699-134">Packaging an Assembly for COM</span></span>](../../../docs/framework/interop/packaging-an-assembly-for-com.md)

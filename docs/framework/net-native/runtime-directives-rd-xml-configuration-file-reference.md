---
title: Laufzeitanweisungs-Konfigurationsdatei (rd.xml) Referenz
ms.date: 03/30/2017
ms.assetid: 8241523f-d8e1-4fb6-bf6a-b29bfe07b38a
ms.openlocfilehash: f4c51dc269775d14d395cb464b3787cc987e086d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128127"
---
# <a name="runtime-directives-rdxml-configuration-file-reference"></a><span data-ttu-id="aa649-102">Laufzeitanweisungs-Konfigurationsdatei (rd.xml) Referenz</span><span class="sxs-lookup"><span data-stu-id="aa649-102">Runtime Directives (rd.xml) Configuration File Reference</span></span>

<span data-ttu-id="aa649-103">Eine Laufzeitanweisungsdatei (.rd.xml) ist eine XML-Konfigurationsdatei, die angibt, ob bestimmte Programmelemente für die Reflektion verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="aa649-103">A runtime directives (.rd.xml) file is an XML configuration file that specifies whether designated program elements are available for reflection.</span></span> <span data-ttu-id="aa649-104">Im Folgenden ist ein Beispiel einer Laufzeitanweisungsdatei angegeben:</span><span class="sxs-lookup"><span data-stu-id="aa649-104">Here’s an example of a runtime directives file:</span></span>

```xml
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
  <Application>
    <Namespace Name="Contoso.Cloud.AppServices" Serialize="Required Public" />
    <Namespace Name="ContosoClient.ViewModels" Serialize="Required Public" />
    <Namespace Name="ContosoClient.DataModel" Serialize="Required Public" />
    <Namespace Name="Contoso.Reader.UtilityLib" Serialize="Required Public" />

    <Namespace Name="System.Collections.ObjectModel" >
      <TypeInstantiation Name="ObservableCollection"
            Arguments="ContosoClient.DataModel.ProductItem" Serialize="Public" />
      <TypeInstantiation Name="ReadOnlyObservableCollection"
            Arguments="ContosoClient.DataModel.ProductGroup" Serialize="Public" />
    </Namespace>
  </Application>
</Directives>
```

## <a name="the-structure-of-a-runtime-directives-file"></a><span data-ttu-id="aa649-105">Die Struktur einer Laufzeitdirektivendatei</span><span class="sxs-lookup"><span data-stu-id="aa649-105">The structure of a runtime directives file</span></span>

<span data-ttu-id="aa649-106">Die Laufzeitdirektivendatei verwendet den Namespace `http://schemas.microsoft.com/netfx/2013/01/metadata`.</span><span class="sxs-lookup"><span data-stu-id="aa649-106">The runtime directives file uses the `http://schemas.microsoft.com/netfx/2013/01/metadata` namespace.</span></span>

<span data-ttu-id="aa649-107">Das Stammelement ist [Directives](directives-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="aa649-107">The root element is the [Directives](directives-element-net-native.md) element.</span></span> <span data-ttu-id="aa649-108">Wie in der folgenden Struktur dargestellt, kann es null oder mehr [Library](library-element-net-native.md)-Elemente und null oder ein [Application](application-element-net-native.md)-Element enthalten.</span><span class="sxs-lookup"><span data-stu-id="aa649-108">It can contain zero or more [Library](library-element-net-native.md) elements, and zero or one [Application](application-element-net-native.md) element, as shown in the following structure.</span></span> <span data-ttu-id="aa649-109">Die Attribute des [Application](application-element-net-native.md)-Elements können eine anwendungsweite Laufzeitreflektionsrichtlinie definieren oder als Container für untergeordnete Elemente dienen.</span><span class="sxs-lookup"><span data-stu-id="aa649-109">The attributes of the [Application](application-element-net-native.md) element can define application-wide runtime reflection policy, or it can serve as a container for child elements.</span></span> <span data-ttu-id="aa649-110">Das [Library](library-element-net-native.md)-Element hingegen ist lediglich ein Container.</span><span class="sxs-lookup"><span data-stu-id="aa649-110">The [Library](library-element-net-native.md) element, on the other hand, is simply a container.</span></span> <span data-ttu-id="aa649-111">Die untergeordneten Elemente der Elemente [Application](application-element-net-native.md) und [Library](library-element-net-native.md) definieren die Typen, Methoden, Felder, Eigenschaften und Ereignisse, die für die Reflektion verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="aa649-111">The children of the [Application](application-element-net-native.md) and [Library](library-element-net-native.md) elements define the types, methods, fields, properties, and events that are available for reflection.</span></span>

<span data-ttu-id="aa649-112">Um Referenzinformationen anzuzeigen, wählen Sie Elemente aus der folgenden Struktur aus, oder lesen Sie unter [Laufzeitanweisungselemente](runtime-directive-elements.md) nach.</span><span class="sxs-lookup"><span data-stu-id="aa649-112">For reference information, choose elements from the following structure or see [Runtime Directive Elements](runtime-directive-elements.md).</span></span> <span data-ttu-id="aa649-113">In der folgenden Hierarchie kennzeichnet die Ellipse eine rekursive Struktur.</span><span class="sxs-lookup"><span data-stu-id="aa649-113">In the following hierarchy, the ellipsis marks a recursive structure.</span></span> <span data-ttu-id="aa649-114">Die Informationen in Klammern zeigen an, ob dieses Element optional oder erforderlich ist, und wenn es verwendet wird, wie viele Instanzen (eine oder viele) zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="aa649-114">The information in brackets indicates whether that element is optional or required, and if it is used, how many instances (one or many) are allowed.</span></span>

<span data-ttu-id="aa649-115">[Direktiven](directives-element-net-native.md) [1:1] [Anwendungs](application-element-net-native.md) [0:1] [Assembly](assembly-element-net-native.md) [0: m] [Namespace](namespace-element-net-native.md) [0: m].</span><span class="sxs-lookup"><span data-stu-id="aa649-115">[Directives](directives-element-net-native.md) [1:1] [Application](application-element-net-native.md) [0:1] [Assembly](assembly-element-net-native.md) [0:M] [Namespace](namespace-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="aa649-116">sein.</span><span class="sxs-lookup"><span data-stu-id="aa649-116">.</span></span> <span data-ttu-id="aa649-117">sein.</span><span class="sxs-lookup"><span data-stu-id="aa649-117">.</span></span>
<span data-ttu-id="aa649-118">[Geben](type-element-net-native.md) Sie [0: M] ein.</span><span class="sxs-lookup"><span data-stu-id="aa649-118">[Type](type-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="aa649-119">sein.</span><span class="sxs-lookup"><span data-stu-id="aa649-119">.</span></span> <span data-ttu-id="aa649-120">sein.</span><span class="sxs-lookup"><span data-stu-id="aa649-120">.</span></span>
<span data-ttu-id="aa649-121">[Typeinstantiations](typeinstantiation-element-net-native.md) (konstruierter generischer Typ) [0: M].</span><span class="sxs-lookup"><span data-stu-id="aa649-121">[TypeInstantiation](typeinstantiation-element-net-native.md) (constructed generic type) [0:M] .</span></span> <span data-ttu-id="aa649-122">sein.</span><span class="sxs-lookup"><span data-stu-id="aa649-122">.</span></span> <span data-ttu-id="aa649-123">sein.</span><span class="sxs-lookup"><span data-stu-id="aa649-123">.</span></span>
<span data-ttu-id="aa649-124">[Namespace](namespace-element-net-native.md) [0: m] [Namespace](namespace-element-net-native.md) [0: m].</span><span class="sxs-lookup"><span data-stu-id="aa649-124">[Namespace](namespace-element-net-native.md) [0:M] [Namespace](namespace-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="aa649-125">sein.</span><span class="sxs-lookup"><span data-stu-id="aa649-125">.</span></span> <span data-ttu-id="aa649-126">sein.</span><span class="sxs-lookup"><span data-stu-id="aa649-126">.</span></span>
<span data-ttu-id="aa649-127">[Geben](type-element-net-native.md) Sie [0: M] ein.</span><span class="sxs-lookup"><span data-stu-id="aa649-127">[Type](type-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="aa649-128">sein.</span><span class="sxs-lookup"><span data-stu-id="aa649-128">.</span></span> <span data-ttu-id="aa649-129">sein.</span><span class="sxs-lookup"><span data-stu-id="aa649-129">.</span></span>
<span data-ttu-id="aa649-130">[Typeinstantiations](typeinstantiation-element-net-native.md) (konstruierter generischer Typ) [0: M].</span><span class="sxs-lookup"><span data-stu-id="aa649-130">[TypeInstantiation](typeinstantiation-element-net-native.md) (constructed generic type) [0:M] .</span></span> <span data-ttu-id="aa649-131">sein.</span><span class="sxs-lookup"><span data-stu-id="aa649-131">.</span></span> <span data-ttu-id="aa649-132">sein.</span><span class="sxs-lookup"><span data-stu-id="aa649-132">.</span></span>
<span data-ttu-id="aa649-133">[Type](type-element-net-native.md) [0: m] [subtypes](subtypes-element-net-native.md) (Unterklassen des enthaltenden Typs) [o:1] [Type](type-element-net-native.md) [0: m].</span><span class="sxs-lookup"><span data-stu-id="aa649-133">[Type](type-element-net-native.md) [0:M] [Subtypes](subtypes-element-net-native.md) (subclasses of the containing type) [O:1] [Type](type-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="aa649-134">sein.</span><span class="sxs-lookup"><span data-stu-id="aa649-134">.</span></span> <span data-ttu-id="aa649-135">sein.</span><span class="sxs-lookup"><span data-stu-id="aa649-135">.</span></span>
<span data-ttu-id="aa649-136">[Typeinstantiations](typeinstantiation-element-net-native.md) (konstruierter generischer Typ) [0: M].</span><span class="sxs-lookup"><span data-stu-id="aa649-136">[TypeInstantiation](typeinstantiation-element-net-native.md) (constructed generic type) [0:M] .</span></span> <span data-ttu-id="aa649-137">sein.</span><span class="sxs-lookup"><span data-stu-id="aa649-137">.</span></span> <span data-ttu-id="aa649-138">sein.</span><span class="sxs-lookup"><span data-stu-id="aa649-138">.</span></span>
<span data-ttu-id="aa649-139">[Attributeimplies](attributeimplies-element-net-native.md) (der enthaltende Typ ist ein Attribut) [o:1] [genericparameter](genericparameter-element-net-native.md) [0: m] [method](method-element-net-native.md) [0: m] [Parameter](parameter-element-net-native.md) [0: m] [typeparameter](typeparameter-element-net-native.md) [0: m] [genericparameter](genericparameter-element-net-native.md) [0: m] [methodinstantiations](methodinstantiation-element-net-native.md) ( konstruierte generische Methode) [0: m] [Eigenschaft](property-element-net-native.md) [0: m] [Feld](field-element-net-native.md) [0: m] [Ereignis](event-element-net-native.md) [0: m] [typeinstantiierung](typeinstantiation-element-net-native.md) (konstruierter generischer Typ) [0: m] [Typ](type-element-net-native.md) [0: m].</span><span class="sxs-lookup"><span data-stu-id="aa649-139">[AttributeImplies](attributeimplies-element-net-native.md) (containing type is an attribute) [O:1] [GenericParameter](genericparameter-element-net-native.md) [0:M] [Method](method-element-net-native.md) [0:M] [Parameter](parameter-element-net-native.md) [0:M] [TypeParameter](typeparameter-element-net-native.md) [0:M] [GenericParameter](genericparameter-element-net-native.md) [0:M] [MethodInstantiation](methodinstantiation-element-net-native.md) (constructed generic method) [0:M] [Property](property-element-net-native.md) [0:M] [Field](field-element-net-native.md) [0:M] [Event](event-element-net-native.md) [0:M] [TypeInstantiation](typeinstantiation-element-net-native.md) (constructed generic type) [0:M] [Type](type-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="aa649-140">sein.</span><span class="sxs-lookup"><span data-stu-id="aa649-140">.</span></span> <span data-ttu-id="aa649-141">sein.</span><span class="sxs-lookup"><span data-stu-id="aa649-141">.</span></span>
<span data-ttu-id="aa649-142">[Typeinstantiations](typeinstantiation-element-net-native.md) (konstruierter generischer Typ) [0: M].</span><span class="sxs-lookup"><span data-stu-id="aa649-142">[TypeInstantiation](typeinstantiation-element-net-native.md) (constructed generic type) [0:M] .</span></span> <span data-ttu-id="aa649-143">sein.</span><span class="sxs-lookup"><span data-stu-id="aa649-143">.</span></span> <span data-ttu-id="aa649-144">sein.</span><span class="sxs-lookup"><span data-stu-id="aa649-144">.</span></span>
<span data-ttu-id="aa649-145">[Method](method-element-net-native.md) [0: m] [Parameter](parameter-element-net-native.md) [0: m] [typeparameter](typeparameter-element-net-native.md) [0: m] [genericparameter](genericparameter-element-net-native.md) [0: m] [methodinstantiations](methodinstantiation-element-net-native.md) (konstruierte generische Methode) [0: m] [Eigenschaft](property-element-net-native.md) [0: m] [Feld](field-element-net-native.md) [0: m] [Ereignis](event-element-net-native.md) [0: m] [ Bibliothek](library-element-net-native.md) [0: m] [Assembly](assembly-element-net-native.md) [0: m] [Namespace](namespace-element-net-native.md) [0: m].</span><span class="sxs-lookup"><span data-stu-id="aa649-145">[Method](method-element-net-native.md) [0:M] [Parameter](parameter-element-net-native.md) [0:M] [TypeParameter](typeparameter-element-net-native.md) [0:M] [GenericParameter](genericparameter-element-net-native.md) [0:M] [MethodInstantiation](methodinstantiation-element-net-native.md) (constructed generic method) [0:M] [Property](property-element-net-native.md) [0:M] [Field](field-element-net-native.md) [0:M] [Event](event-element-net-native.md) [0:M] [Library](library-element-net-native.md) [0:M] [Assembly](assembly-element-net-native.md) [0:M] [Namespace](namespace-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="aa649-146">sein.</span><span class="sxs-lookup"><span data-stu-id="aa649-146">.</span></span> <span data-ttu-id="aa649-147">sein.</span><span class="sxs-lookup"><span data-stu-id="aa649-147">.</span></span>
<span data-ttu-id="aa649-148">[Geben](type-element-net-native.md) Sie [0: M] ein.</span><span class="sxs-lookup"><span data-stu-id="aa649-148">[Type](type-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="aa649-149">sein.</span><span class="sxs-lookup"><span data-stu-id="aa649-149">.</span></span> <span data-ttu-id="aa649-150">sein.</span><span class="sxs-lookup"><span data-stu-id="aa649-150">.</span></span>
<span data-ttu-id="aa649-151">[Typeinstantiations](typeinstantiation-element-net-native.md) (konstruierter generischer Typ) [0: M].</span><span class="sxs-lookup"><span data-stu-id="aa649-151">[TypeInstantiation](typeinstantiation-element-net-native.md) (constructed generic type) [0:M] .</span></span> <span data-ttu-id="aa649-152">sein.</span><span class="sxs-lookup"><span data-stu-id="aa649-152">.</span></span> <span data-ttu-id="aa649-153">sein.</span><span class="sxs-lookup"><span data-stu-id="aa649-153">.</span></span>
<span data-ttu-id="aa649-154">[Namespace](namespace-element-net-native.md) [0: m] [Namespace](namespace-element-net-native.md) [0: m].</span><span class="sxs-lookup"><span data-stu-id="aa649-154">[Namespace](namespace-element-net-native.md) [0:M] [Namespace](namespace-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="aa649-155">sein.</span><span class="sxs-lookup"><span data-stu-id="aa649-155">.</span></span> <span data-ttu-id="aa649-156">sein.</span><span class="sxs-lookup"><span data-stu-id="aa649-156">.</span></span>
<span data-ttu-id="aa649-157">[Geben](type-element-net-native.md) Sie [0: M] ein.</span><span class="sxs-lookup"><span data-stu-id="aa649-157">[Type](type-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="aa649-158">sein.</span><span class="sxs-lookup"><span data-stu-id="aa649-158">.</span></span> <span data-ttu-id="aa649-159">sein.</span><span class="sxs-lookup"><span data-stu-id="aa649-159">.</span></span>
<span data-ttu-id="aa649-160">[Typeinstantiations](typeinstantiation-element-net-native.md) (konstruierter generischer Typ) [0: M].</span><span class="sxs-lookup"><span data-stu-id="aa649-160">[TypeInstantiation](typeinstantiation-element-net-native.md) (constructed generic type) [0:M] .</span></span> <span data-ttu-id="aa649-161">sein.</span><span class="sxs-lookup"><span data-stu-id="aa649-161">.</span></span> <span data-ttu-id="aa649-162">sein.</span><span class="sxs-lookup"><span data-stu-id="aa649-162">.</span></span>
<span data-ttu-id="aa649-163">[Type](type-element-net-native.md) [0: m] [subtypes](subtypes-element-net-native.md) (Unterklassen des enthaltenden Typs) [o:1] [Type](type-element-net-native.md) [0: m].</span><span class="sxs-lookup"><span data-stu-id="aa649-163">[Type](type-element-net-native.md) [0:M] [Subtypes](subtypes-element-net-native.md) (subclasses of the containing type) [O:1] [Type](type-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="aa649-164">sein.</span><span class="sxs-lookup"><span data-stu-id="aa649-164">.</span></span> <span data-ttu-id="aa649-165">sein.</span><span class="sxs-lookup"><span data-stu-id="aa649-165">.</span></span>
<span data-ttu-id="aa649-166">[Typeinstantiations](typeinstantiation-element-net-native.md) (konstruierter generischer Typ) [0: M].</span><span class="sxs-lookup"><span data-stu-id="aa649-166">[TypeInstantiation](typeinstantiation-element-net-native.md) (constructed generic type) [0:M] .</span></span> <span data-ttu-id="aa649-167">sein.</span><span class="sxs-lookup"><span data-stu-id="aa649-167">.</span></span> <span data-ttu-id="aa649-168">sein.</span><span class="sxs-lookup"><span data-stu-id="aa649-168">.</span></span>
<span data-ttu-id="aa649-169">[Attributeimplies](attributeimplies-element-net-native.md) (der enthaltende Typ ist ein Attribut) [o:1] [genericparameter](genericparameter-element-net-native.md) [0: m] [method](method-element-net-native.md) [0: m] [methodinstantiations](methodinstantiation-element-net-native.md) (konstruierte generische Methode) [0: m] [Eigenschaft](property-element-net-native.md) [0: m] [Feld](field-element-net-native.md) [0: m] [Ereignis](event-element-net-native.md) [0 : M] [typeinstantiung](typeinstantiation-element-net-native.md) (konstruierter generischer Typ) [0: m] [Typ](type-element-net-native.md) [0: m].</span><span class="sxs-lookup"><span data-stu-id="aa649-169">[AttributeImplies](attributeimplies-element-net-native.md) (containing type is an attribute) [O:1] [GenericParameter](genericparameter-element-net-native.md) [0:M] [Method](method-element-net-native.md) [0:M] [MethodInstantiation](methodinstantiation-element-net-native.md) (constructed generic method) [0:M] [Property](property-element-net-native.md) [0:M] [Field](field-element-net-native.md) [0:M] [Event](event-element-net-native.md) [0:M] [TypeInstantiation](typeinstantiation-element-net-native.md) (constructed generic type) [0:M] [Type](type-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="aa649-170">sein.</span><span class="sxs-lookup"><span data-stu-id="aa649-170">.</span></span> <span data-ttu-id="aa649-171">sein.</span><span class="sxs-lookup"><span data-stu-id="aa649-171">.</span></span>
<span data-ttu-id="aa649-172">[Typeinstantiations](typeinstantiation-element-net-native.md) (konstruierter generischer Typ) [0: M].</span><span class="sxs-lookup"><span data-stu-id="aa649-172">[TypeInstantiation](typeinstantiation-element-net-native.md) (constructed generic type) [0:M] .</span></span> <span data-ttu-id="aa649-173">sein.</span><span class="sxs-lookup"><span data-stu-id="aa649-173">.</span></span> <span data-ttu-id="aa649-174">sein.</span><span class="sxs-lookup"><span data-stu-id="aa649-174">.</span></span>
<span data-ttu-id="aa649-175">[Method](method-element-net-native.md) [0: m] [methodinstantiations](methodinstantiation-element-net-native.md) (konstruierte generische Methode) [0: m] [Eigenschaft](property-element-net-native.md) [0: m] [Field](field-element-net-native.md) [0: m] [Ereignis](event-element-net-native.md) [0: m]</span><span class="sxs-lookup"><span data-stu-id="aa649-175">[Method](method-element-net-native.md) [0:M] [MethodInstantiation](methodinstantiation-element-net-native.md) (constructed generic method) [0:M] [Property](property-element-net-native.md) [0:M] [Field](field-element-net-native.md) [0:M] [Event](event-element-net-native.md) [0:M]</span></span>

<span data-ttu-id="aa649-176">Das [Application](application-element-net-native.md)-Element kann entweder keine Attribute oder die im [Abschnitt zu Laufzeitanweisungen und -richtlinien](#Directives) beschriebenen Richtlinienattribute besitzen.</span><span class="sxs-lookup"><span data-stu-id="aa649-176">The [Application](application-element-net-native.md) element can have no attributes, or it can have the policy attributes discussed in the [Runtime directive and policy section](#Directives).</span></span>

<span data-ttu-id="aa649-177">Ein [Library](library-element-net-native.md)-Element verfügt über ein einzelnes Attribut, `Name`, das den Namen einer Bibliothek oder die Assembly ohne Dateierweiterung angibt.</span><span class="sxs-lookup"><span data-stu-id="aa649-177">A [Library](library-element-net-native.md) element has a single attribute, `Name`, that specifies the name of a library or assembly, without its file extension.</span></span> <span data-ttu-id="aa649-178">Das folgende [Library](library-element-net-native.md)-Element gilt z.B. für eine Assembly namens Extensions.dll.</span><span class="sxs-lookup"><span data-stu-id="aa649-178">For example, the following [Library](library-element-net-native.md) element applies to an assembly named Extensions.dll.</span></span>

```xml
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
  <Application>
     <!-- Child elements go here -->
  </Application>
  <Library Name="Extensions">
     <!-- Child elements go here -->
  </Library>
</Directives>
```

<a name="Directives"></a>

## <a name="runtime-directives-and-policy"></a><span data-ttu-id="aa649-179">Laufzeitanweisungen und -richtlinien</span><span class="sxs-lookup"><span data-stu-id="aa649-179">Runtime directives and policy</span></span>

<span data-ttu-id="aa649-180">Das [Application](application-element-net-native.md)-Element und die untergeordneten Elemente der Elemente [Library](library-element-net-native.md) und [Application](application-element-net-native.md) drücken die Richtlinie aus. Das heißt, sie definieren, wie eine App Reflektion auf ein Programmelement anwenden kann.</span><span class="sxs-lookup"><span data-stu-id="aa649-180">The [Application](application-element-net-native.md) element itself and the child elements of the [Library](library-element-net-native.md) and [Application](application-element-net-native.md) elements express policy; that is, they define the way in which an app can apply reflection to a program element.</span></span> <span data-ttu-id="aa649-181">Der Richtlinientyp wird von einem Attribut des Elements definiert (z. B. `Serialize`).</span><span class="sxs-lookup"><span data-stu-id="aa649-181">The policy type is defined by an attribute of the element (for example, `Serialize`).</span></span> <span data-ttu-id="aa649-182">Der Richtlinienwert wird vom Wert des Attributs definiert (z. B. `Serialize="Required"`).</span><span class="sxs-lookup"><span data-stu-id="aa649-182">The policy value is defined by the attribute’s value (for example, `Serialize="Required"`).</span></span>

<span data-ttu-id="aa649-183">Jede durch ein Attribut eines Elements angegebene Richtlinie gilt für alle untergeordneten Elemente, die keinen Wert für diese Richtlinie angeben.</span><span class="sxs-lookup"><span data-stu-id="aa649-183">Any policy specified by an attribute of an element applies to all child elements that don’t specify a value for that policy.</span></span> <span data-ttu-id="aa649-184">Wird z.B. eine Richtlinie durch ein [Type](type-element-net-native.md)-Element angegeben, gilt diese Richtlinie für alle enthaltenen Typen und Member, für die nicht explizit eine Richtlinie angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="aa649-184">For example, if a policy is specified by a [Type](type-element-net-native.md) element, that policy applies to all contained types and members for which a policy is not explicitly specified.</span></span>

<span data-ttu-id="aa649-185">Die Richtlinie, die durch die Elemente [Application](application-element-net-native.md), [Assembly](assembly-element-net-native.md), [AttributeImplies](attributeimplies-element-net-native.md), [Namespace](namespace-element-net-native.md), [Subtypes](subtypes-element-net-native.md) und [Type](type-element-net-native.md) ausgedrückt werden kann, unterscheidet sich von der Richtlinie, die für einzelne Member ausgedrückt werden kann (durch die Elemente [Method](method-element-net-native.md), [Property](property-element-net-native.md), [Field](field-element-net-native.md) und [Event](event-element-net-native.md)).</span><span class="sxs-lookup"><span data-stu-id="aa649-185">The policy that can be expressed by the [Application](application-element-net-native.md), [Assembly](assembly-element-net-native.md), [AttributeImplies](attributeimplies-element-net-native.md), [Namespace](namespace-element-net-native.md), [Subtypes](subtypes-element-net-native.md), and [Type](type-element-net-native.md) elements differs from the policy that can be expressed for individual members (by the [Method](method-element-net-native.md), [Property](property-element-net-native.md), [Field](field-element-net-native.md), and [Event](event-element-net-native.md) elements).</span></span>

### <a name="specifying-policy-for-assemblies-namespaces-and-types"></a><span data-ttu-id="aa649-186">Festlegen von Richtlinien für Assemblys, Namespaces und Typen</span><span class="sxs-lookup"><span data-stu-id="aa649-186">Specifying policy for assemblies, namespaces, and types</span></span>

<span data-ttu-id="aa649-187">Die Elemente [Application](application-element-net-native.md), [Assembly](assembly-element-net-native.md), [AttributeImplies](attributeimplies-element-net-native.md), [Namespace](namespace-element-net-native.md), [Subtypes](subtypes-element-net-native.md) und [Type](type-element-net-native.md) unterstützen folgende Richtlinientypen:</span><span class="sxs-lookup"><span data-stu-id="aa649-187">The [Application](application-element-net-native.md), [Assembly](assembly-element-net-native.md), [AttributeImplies](attributeimplies-element-net-native.md), [Namespace](namespace-element-net-native.md), [Subtypes](subtypes-element-net-native.md), and [Type](type-element-net-native.md) elements support the following policy types:</span></span>

- <span data-ttu-id="aa649-188">`Activate`</span><span class="sxs-lookup"><span data-stu-id="aa649-188">`Activate`.</span></span> <span data-ttu-id="aa649-189">Steuert den Laufzeitzugriff auf Konstruktoren, um die Aktivierung von Instanzen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="aa649-189">Controls runtime access to constructors, to enable activation of instances.</span></span>

- <span data-ttu-id="aa649-190">`Browse`</span><span class="sxs-lookup"><span data-stu-id="aa649-190">`Browse`.</span></span> <span data-ttu-id="aa649-191">Steuert das Abfragen von Informationen über Programmelemente, ermöglicht jedoch keinen Laufzeitzugriff.</span><span class="sxs-lookup"><span data-stu-id="aa649-191">Controls querying for information about program elements but does not enable any runtime access.</span></span>

- <span data-ttu-id="aa649-192">`Dynamic`</span><span class="sxs-lookup"><span data-stu-id="aa649-192">`Dynamic`.</span></span> <span data-ttu-id="aa649-193">Steuert den Laufzeitzugriff auf alle Typmember, einschließlich Konstruktoren, Methoden, Felder, Eigenschaften und Ereignisse, um die dynamische Programmierung zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="aa649-193">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>

- <span data-ttu-id="aa649-194">`Serialize`</span><span class="sxs-lookup"><span data-stu-id="aa649-194">`Serialize`.</span></span> <span data-ttu-id="aa649-195">Steuert den Laufzeitzugriff auf Konstruktoren, Felder und Eigenschaften, um Serialisierung und Deserialisierung von Typinstanzen durch Bibliotheken von Drittanbietern wie das Newtonsoft JSON-Serialisierungsprogramm zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="aa649-195">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and serialized by third-party libraries such as the Newtonsoft JSON serializer.</span></span>

- <span data-ttu-id="aa649-196">`DataContractSerializer`</span><span class="sxs-lookup"><span data-stu-id="aa649-196">`DataContractSerializer`.</span></span> <span data-ttu-id="aa649-197">Steuert die Richtlinie für die Serialisierung, die die <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>-Klasse verwendet.</span><span class="sxs-lookup"><span data-stu-id="aa649-197">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>

- <span data-ttu-id="aa649-198">`DataContractJsonSerializer`</span><span class="sxs-lookup"><span data-stu-id="aa649-198">`DataContractJsonSerializer`.</span></span> <span data-ttu-id="aa649-199">Steuert die Richtlinie für die JSON-Serialisierung, die die <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>-Klasse verwendet.</span><span class="sxs-lookup"><span data-stu-id="aa649-199">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>

- <span data-ttu-id="aa649-200">`XmlSerializer`</span><span class="sxs-lookup"><span data-stu-id="aa649-200">`XmlSerializer`.</span></span> <span data-ttu-id="aa649-201">Steuert die Richtlinie für die XML-Serialisierung, die die <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>-Klasse verwendet.</span><span class="sxs-lookup"><span data-stu-id="aa649-201">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>

- <span data-ttu-id="aa649-202">`MarshalObject`</span><span class="sxs-lookup"><span data-stu-id="aa649-202">`MarshalObject`.</span></span> <span data-ttu-id="aa649-203">Steuert die Richtlinie für das Marshalling von Verweistypen zu WinRT und COM.</span><span class="sxs-lookup"><span data-stu-id="aa649-203">Controls policy for marshaling reference types to WinRT and COM.</span></span>

- <span data-ttu-id="aa649-204">`MarshalDelegate`</span><span class="sxs-lookup"><span data-stu-id="aa649-204">`MarshalDelegate`.</span></span> <span data-ttu-id="aa649-205">Steuert die Richtlinie für das Marshalling von Delegattypen als Funktionszeiger zu systemeigenem Code.</span><span class="sxs-lookup"><span data-stu-id="aa649-205">Controls policy for marshaling delegate types as function pointers to native code.</span></span>

- <span data-ttu-id="aa649-206">`MarshalStructure` .</span><span class="sxs-lookup"><span data-stu-id="aa649-206">`MarshalStructure` .</span></span> <span data-ttu-id="aa649-207">Steuert die Richtlinie für das Marshalling von Strukturen zu nativem Code.</span><span class="sxs-lookup"><span data-stu-id="aa649-207">Controls policy for marshaling structures to native code.</span></span>

<span data-ttu-id="aa649-208">Die Einstellungen für diese Richtlinientypen sind:</span><span class="sxs-lookup"><span data-stu-id="aa649-208">The settings associated with these policy types are:</span></span>

- <span data-ttu-id="aa649-209">`All`</span><span class="sxs-lookup"><span data-stu-id="aa649-209">`All`.</span></span> <span data-ttu-id="aa649-210">Aktiviert die Richtlinie für alle Typen und Member, die die Toolkette nicht entfernt.</span><span class="sxs-lookup"><span data-stu-id="aa649-210">Enable the policy for all types and members that the tool chain does not remove.</span></span>

- <span data-ttu-id="aa649-211">`Auto`</span><span class="sxs-lookup"><span data-stu-id="aa649-211">`Auto`.</span></span> <span data-ttu-id="aa649-212">Verwendet das Standardverhalten.</span><span class="sxs-lookup"><span data-stu-id="aa649-212">Use the default behavior.</span></span> <span data-ttu-id="aa649-213">(Fehlende Angabe einer Richtlinie entspricht dem Festlegen der Richtlinie auf `Auto`, sofern die Richtlinie nicht, beispielsweise durch ein übergeordnetes Element, überschrieben wird.)</span><span class="sxs-lookup"><span data-stu-id="aa649-213">(Not specifying a policy is equivalent to setting that policy to `Auto` unless that policy is overridden, for example by a parent element.)</span></span>

- <span data-ttu-id="aa649-214">`Excluded`</span><span class="sxs-lookup"><span data-stu-id="aa649-214">`Excluded`.</span></span> <span data-ttu-id="aa649-215">Deaktiviert die Richtlinie für das Programmelement.</span><span class="sxs-lookup"><span data-stu-id="aa649-215">Disable the policy for the program element.</span></span>

- <span data-ttu-id="aa649-216">`Public`</span><span class="sxs-lookup"><span data-stu-id="aa649-216">`Public`.</span></span> <span data-ttu-id="aa649-217">Aktiviert die Richtlinie für öffentliche Typen oder Member, sofern die Toolkette nicht bestimmt, dass der Member unnötig ist und daher entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="aa649-217">Enable the policy for public types or members unless the tool chain determines that the member is unnecessary and therefore removes it.</span></span> <span data-ttu-id="aa649-218">(In letzterem Fall müssen Sie `Required Public` verwenden, um sicherzustellen, dass der Member beibehalten wird und über Reflektionsfunktionen verfügt.)</span><span class="sxs-lookup"><span data-stu-id="aa649-218">(In the latter case, you must use `Required Public` to ensure that the member is kept and has reflection capabilities.)</span></span>

- <span data-ttu-id="aa649-219">`PublicAndInternal`</span><span class="sxs-lookup"><span data-stu-id="aa649-219">`PublicAndInternal`.</span></span> <span data-ttu-id="aa649-220">Aktiviert die Richtlinie für öffentliche und interne Typen oder Member, sofern die Toolkette diese nicht entfernt.</span><span class="sxs-lookup"><span data-stu-id="aa649-220">Enable the policy for public and internal types or members if the tool chain doesn't remove them.</span></span>

- <span data-ttu-id="aa649-221">`Required Public`</span><span class="sxs-lookup"><span data-stu-id="aa649-221">`Required Public`.</span></span> <span data-ttu-id="aa649-222">Fordert, dass die Toolkette öffentliche Typen und Member unabhängig von ihrer Verwendung beibehält und die Richtlinie für sie aktiviert.</span><span class="sxs-lookup"><span data-stu-id="aa649-222">Require the tool chain to keep public types and members whether or not they are used, and enable the policy for them.</span></span>

- <span data-ttu-id="aa649-223">`Required PublicAndInternal`</span><span class="sxs-lookup"><span data-stu-id="aa649-223">`Required PublicAndInternal`.</span></span> <span data-ttu-id="aa649-224">Fordert, dass die Toolkette öffentliche und interne Typen und Member unabhängig von ihrer Verwendung beibehält und die Richtlinie für sie aktiviert.</span><span class="sxs-lookup"><span data-stu-id="aa649-224">Require the tool chain to keep both public and internal types and members whether or not they are used, and enable the policy for them.</span></span>

- <span data-ttu-id="aa649-225">`Required All`</span><span class="sxs-lookup"><span data-stu-id="aa649-225">`Required All`.</span></span> <span data-ttu-id="aa649-226">Fordert, dass die Toolkette alle Typen und Member unabhängig von ihrer Verwendung beibehält und die Richtlinie für sie aktiviert.</span><span class="sxs-lookup"><span data-stu-id="aa649-226">Require the tool chain to keep all types and members whether or not they are used, and enable the policy for them.</span></span>

<span data-ttu-id="aa649-227">Die folgende Laufzeitanweisungsdatei definiert z. B. die Richtlinie für alle Typen und Member in der Assembly DataClasses.dll.</span><span class="sxs-lookup"><span data-stu-id="aa649-227">For example, the following runtime directives file defines policy for all types and members in the assembly DataClasses.dll.</span></span> <span data-ttu-id="aa649-228">Sie aktiviert die Reflektion für die Serialisierung aller öffentlichen Eigenschaften, ermöglicht das Durchsuchen nach allen Typen und Typmembern (aufgrund des `Dynamic`-Attributs) und aktiviert die Reflektion für alle öffentlichen Typen und Member.</span><span class="sxs-lookup"><span data-stu-id="aa649-228">It enables reflection for serialization of all public properties, enables browsing for all types and type members, enables activation for all types (because of the `Dynamic` attribute), and enables reflection for all public types and members.</span></span>

```xml
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
   <Application>
      <Assembly Name="DataClasses" Serialize="Required Public"
                Browse="All" Activate="PublicAndInternal"
                Dynamic="Public"  />
   </Application>
   <Library Name="UtilityLibrary">
     <!-- Child elements go here -->
   </Library>
</Directives>
```

### <a name="specifying-policy-for-members"></a><span data-ttu-id="aa649-229">Festlegen von Richtlinien für Member</span><span class="sxs-lookup"><span data-stu-id="aa649-229">Specifying policy for members</span></span>

<span data-ttu-id="aa649-230">Die Elemente [Property](property-element-net-native.md) und [Field](field-element-net-native.md) unterstützen die folgenden Richtlinientypen:</span><span class="sxs-lookup"><span data-stu-id="aa649-230">The [Property](property-element-net-native.md) and [Field](field-element-net-native.md) elements support the following policy types:</span></span>

- <span data-ttu-id="aa649-231">`Browse` - Steuert das Abfragen von Informationen über diesen Member, aber ermöglicht keinen Laufzeitzugriff.</span><span class="sxs-lookup"><span data-stu-id="aa649-231">`Browse` - Controls querying for information about this member but does not enable any runtime access.</span></span>

- <span data-ttu-id="aa649-232">`Dynamic` - Steuert den Laufzeitzugriff auf alle Typmember, einschließlich Konstruktoren, Methoden, Felder, Eigenschaften und Ereignisse, um die dynamische Programmierung zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="aa649-232">`Dynamic` - Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span> <span data-ttu-id="aa649-233">Steuert auch das Abfragen von Informationen über den enthaltenden Typ.</span><span class="sxs-lookup"><span data-stu-id="aa649-233">Also controls querying for information about the containing type.</span></span>

- <span data-ttu-id="aa649-234">`Serialize` - Steuert den Laufzeitzugriff auf den Member, um Serialisierung und Deserialisierung von Typinstanzen durch Bibliotheken wie das Newtonsoft JSON-Serialisierungsprogramm zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="aa649-234">`Serialize` - Controls runtime access to the member to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span> <span data-ttu-id="aa649-235">Diese Richtlinie kann auf Konstruktoren, Felder und Eigenschaften angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="aa649-235">This policy can be applied to constructors, fields, and properties.</span></span>

<span data-ttu-id="aa649-236">Die Elemente [Method](method-element-net-native.md) und [Event](event-element-net-native.md) unterstützen die folgenden Richtlinientypen:</span><span class="sxs-lookup"><span data-stu-id="aa649-236">The [Method](method-element-net-native.md) and [Event](event-element-net-native.md) elements support the following policy types:</span></span>

- <span data-ttu-id="aa649-237">`Browse` - Steuert das Abfragen von Informationen über diesen Member, aber ermöglicht keinen Laufzeitzugriff.</span><span class="sxs-lookup"><span data-stu-id="aa649-237">`Browse` - Controls querying for information about this member but doesn’t enable any runtime access.</span></span>

- <span data-ttu-id="aa649-238">`Dynamic` - Steuert den Laufzeitzugriff auf alle Typmember, einschließlich Konstruktoren, Methoden, Felder, Eigenschaften und Ereignisse, um die dynamische Programmierung zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="aa649-238">`Dynamic` - Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span> <span data-ttu-id="aa649-239">Steuert auch das Abfragen von Informationen über den enthaltenden Typ.</span><span class="sxs-lookup"><span data-stu-id="aa649-239">Also controls querying for information about the containing type.</span></span>

 <span data-ttu-id="aa649-240">Die Einstellungen für diese Richtlinientypen sind:</span><span class="sxs-lookup"><span data-stu-id="aa649-240">The settings associated with these policy types are:</span></span>

- <span data-ttu-id="aa649-241">`Auto` - Standardverhalten verwenden.</span><span class="sxs-lookup"><span data-stu-id="aa649-241">`Auto` - Use the default behavior.</span></span> <span data-ttu-id="aa649-242">(Fehlende Angabe einer Richtlinie entspricht dem Festlegen der Richtlinie auf `Auto`, sofern sie nicht überschrieben wird.)</span><span class="sxs-lookup"><span data-stu-id="aa649-242">(Not specifying a policy is equivalent to setting that policy to `Auto` unless something overrides it.)</span></span>

- <span data-ttu-id="aa649-243">`Excluded` - Nie Metadaten für den Member einschließen.</span><span class="sxs-lookup"><span data-stu-id="aa649-243">`Excluded` - Never include metadata for the member.</span></span>

- <span data-ttu-id="aa649-244">`Included` - Die Richtlinie aktivieren, wenn der übergeordnete Typ in der Ausgabe vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="aa649-244">`Included` - Enable the policy if the parent type is present in the output.</span></span>

- <span data-ttu-id="aa649-245">`Required` - Die Toolkette soll diesen Member beibehalten, auch wenn er anscheinend nicht verwendet wird, und die Richtlinie dafür aktivieren.</span><span class="sxs-lookup"><span data-stu-id="aa649-245">`Required` - Require the tool chain to keep this member even if appears to be unused, and enable policy for it.</span></span>

## <a name="runtime-directives-file-semantics"></a><span data-ttu-id="aa649-246">Semantik der Laufzeitdirektivendatei</span><span class="sxs-lookup"><span data-stu-id="aa649-246">Runtime directives file semantics</span></span>

<span data-ttu-id="aa649-247">Die Richtlinie kann gleichzeitig für Elemente höherer und niedrigerer Ebenen definiert werden.</span><span class="sxs-lookup"><span data-stu-id="aa649-247">Policy can be defined simultaneously for both higher-level and lower-level elements.</span></span> <span data-ttu-id="aa649-248">Die Richtlinie kann z. B. für eine Assembly und für einige Typen in dieser Assembly definiert werden.</span><span class="sxs-lookup"><span data-stu-id="aa649-248">For example, policy can be defined for an assembly, and for some of the types contained in that assembly.</span></span> <span data-ttu-id="aa649-249">Wenn ein bestimmtes Element auf niedrigerer Ebene nicht dargestellt wird, erbt es die Richtlinie des übergeordneten Objekts.</span><span class="sxs-lookup"><span data-stu-id="aa649-249">If a particular lower-level element is not represented, it inherits the policy of its parent.</span></span> <span data-ttu-id="aa649-250">Wenn z. B. ein `Assembly`-Element vorhanden ist, aber keine `Type` Elemente, gilt die im `Assembly`-Element angegebene Richtlinie für alle Typen in der Assembly.</span><span class="sxs-lookup"><span data-stu-id="aa649-250">For example, if an `Assembly` element is present but `Type` elements are not, the policy specified in the `Assembly` element applies to each type in the assembly.</span></span> <span data-ttu-id="aa649-251">Mehrere Elemente können auch eine Richtlinie auf dasselbe Programmelement anwenden.</span><span class="sxs-lookup"><span data-stu-id="aa649-251">Multiple elements can also apply policy to the same program element.</span></span> <span data-ttu-id="aa649-252">Zum Beispiel können verschiedene [Assembly](assembly-element-net-native.md)-Elemente dasselbe Richtlinienelement für dieselbe Assembly unterschiedlich definieren.</span><span class="sxs-lookup"><span data-stu-id="aa649-252">For example, separate [Assembly](assembly-element-net-native.md) elements might define the same policy element for the same assembly differently.</span></span> <span data-ttu-id="aa649-253">In den folgenden Abschnitten wird erläutert, wie die Richtlinie für einen bestimmten Typ in diesen Fällen aufgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="aa649-253">The following sections explain how the policy for a particular type is resolved in those cases.</span></span>

<span data-ttu-id="aa649-254">Ein [Type](type-element-net-native.md)- oder [Method](method-element-net-native.md)-Element eines generischen Typs oder einer generischen Methode wendet seine Richtlinie auf alle Instanziierungen an, die keine eigene Richtlinie haben.</span><span class="sxs-lookup"><span data-stu-id="aa649-254">A [Type](type-element-net-native.md) or [Method](method-element-net-native.md) element of a generic type or method applies its policy to all instantiations that do not have their own policy.</span></span> <span data-ttu-id="aa649-255">Beispielsweise gilt ein `Type`-Element, das eine Richtlinie für <xref:System.Collections.Generic.List%601> angibt, für alle konstruierten Instanzen dieses generischen Typs, sofern es nicht für einen bestimmten konstruierten generischen Typ (z. B. `List<Int32>`) durch ein `TypeInstantiation`-Element überschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="aa649-255">For example, a `Type` element that specifies policy for <xref:System.Collections.Generic.List%601> applies to all constructed instances of that generic type, unless it's overridden for a particular constructed generic type (such as a `List<Int32>`) by a `TypeInstantiation` element.</span></span> <span data-ttu-id="aa649-256">Andernfalls definieren Elemente Richtlinien für das genannte Programmelement.</span><span class="sxs-lookup"><span data-stu-id="aa649-256">Otherwise, elements define policy for the program element named.</span></span>

<span data-ttu-id="aa649-257">Wenn ein Element mehreindeutig ist, sucht die Engine nach Übereinstimmungen, und wenn eine genaue Übereinstimmung gefunden wird, wird sie verwendet.</span><span class="sxs-lookup"><span data-stu-id="aa649-257">When an element is ambiguous, the engine looks for matches, and if it finds an exact match, it will use it.</span></span> <span data-ttu-id="aa649-258">Wenn mehrere Übereinstimmungen gefunden werden, wird eine Warnung oder ein Fehler ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="aa649-258">If it finds multiple matches, there will be a warning or error.</span></span>

### <a name="if-two-directives-apply-policy-to-the-same-program-element"></a><span data-ttu-id="aa649-259">Wenn zwei Direktiven Richtlinien auf das gleiche Programmelement anwenden</span><span class="sxs-lookup"><span data-stu-id="aa649-259">If two directives apply policy to the same program element</span></span>

<span data-ttu-id="aa649-260">Wenn zwei Elemente in verschiedenen Laufzeitanweisungsdateien versuchen, denselben Richtlinientyp für dasselbe Programmelement (z. B. eine Assembly oder einen Typ) auf unterschiedliche Werte festzulegen, wird der Konflikt wie folgt aufgelöst:</span><span class="sxs-lookup"><span data-stu-id="aa649-260">If two elements in different runtime directives files try to set the same policy type for the same program element (such as an assembly or type) to different values, the conflict is resolved as follows:</span></span>

1. <span data-ttu-id="aa649-261">Wenn das `Excluded`-Element vorhanden ist, hat es Vorrang.</span><span class="sxs-lookup"><span data-stu-id="aa649-261">If the `Excluded` element is present, it has precedence.</span></span>

2. <span data-ttu-id="aa649-262">`Required` hat Vorrang vor nicht `Required`.</span><span class="sxs-lookup"><span data-stu-id="aa649-262">`Required` has precedence over not `Required`.</span></span>

3. <span data-ttu-id="aa649-263">`All` hat Vorrang vor `PublicAndInternal`, das wiederum Vorrang vor `Public` hat.</span><span class="sxs-lookup"><span data-stu-id="aa649-263">`All` has precedence over `PublicAndInternal`, which has precedence over `Public`.</span></span>

4. <span data-ttu-id="aa649-264">Eine explizite Einstellung hat Vorrang vor `Auto`.</span><span class="sxs-lookup"><span data-stu-id="aa649-264">Any explicit setting has precedence over `Auto`.</span></span>

<span data-ttu-id="aa649-265">Wenn beispielsweise ein einzelnes Projekt die folgenden beiden Laufzeitdirektivendateien enthält, wird die Serialisierungsrichtlinie für DataClasses.dll auf `Required Public` und `All` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="aa649-265">For example, if a single project includes the following two runtime directives files, the serialization policy for DataClasses.dll is set to both `Required Public` and `All`.</span></span> <span data-ttu-id="aa649-266">In diesem Fall wird die Serialisierungsrichtlinie zu `Required All` aufgelöst.</span><span class="sxs-lookup"><span data-stu-id="aa649-266">In this case, the serialization policy would be resolved as `Required All`.</span></span>

```xml
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
   <Application>
      <Assembly Name="DataClasses" Serialize="Required Public"/>
   </Application>
   <Library Name="DataClasses">
      <!-- any other elements -->
   </Library>
</Directives>
```

```xml
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
   <Application>
      <Assembly Name="DataClasses" Serialize="All" />
   </Application>
   <Library Name="DataClasses">
      <!-- any other elements -->
   </Library>
</Directives>
```

<span data-ttu-id="aa649-267">Wenn jedoch zwei Direktiven in einer einzelnen Laufzeitdirektivendatei versuchen, denselben Richtlinientyp für dasselbe Programmelement festlegen, zeigt das XML-Schemadefinitionstool eine Fehlermeldung an.</span><span class="sxs-lookup"><span data-stu-id="aa649-267">However, if two directives in a single runtime directives file try to set the same policy type for the same program element, the XML Scheme Definition tool displays an error message.</span></span>

### <a name="if-child-and-parent-elements-apply-the-same-policy-type"></a><span data-ttu-id="aa649-268">Wenn die untergeordneten und übergeordneten Elemente denselben Richtlinientyp anwenden</span><span class="sxs-lookup"><span data-stu-id="aa649-268">If child and parent elements apply the same policy type</span></span>

<span data-ttu-id="aa649-269">Untergeordnete Elemente überschreiben ihre übergeordneten Elemente, einschließlich der Einstellung `Excluded`.</span><span class="sxs-lookup"><span data-stu-id="aa649-269">Child elements override their parent elements, including the `Excluded` setting.</span></span> <span data-ttu-id="aa649-270">Überschreiben ist der wichtigste Grund, warum Sie `Auto` angeben sollten.</span><span class="sxs-lookup"><span data-stu-id="aa649-270">Overriding is the main reason you would want to specify `Auto`.</span></span>

<span data-ttu-id="aa649-271">Im folgenden Beispiel lautet die Serialisierungsrichtlinieneinstellung für alles in `DataClasses`, was nicht in `DataClasses.ViewModels` ist, `Required Public`, und alles, was in `DataClasses` und `DataClasses.ViewModels` ist, lautet `All`.</span><span class="sxs-lookup"><span data-stu-id="aa649-271">In the following example, the serialization policy setting for everything in `DataClasses` that’s not in `DataClasses.ViewModels` would be `Required Public`, and everything that's in both `DataClasses` and `DataClasses.ViewModels` would be `All`.</span></span>

```xml
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
   <Application>
      <Assembly Name="DataClasses" Serialize="Required Public" >
         <Namespace Name="DataClasses.ViewModels" Serialize="All" />
      </Assembly>
   </Application>
   <Library Name="DataClasses">
      <!-- any other elements -->
   </Library>
</Directives>
```

### <a name="if-open-generics-and-instantiated-elements-apply-the-same-policy-type"></a><span data-ttu-id="aa649-272">Wenn offene Generics und instanziierte Elemente denselben Richtlinientyp anwenden</span><span class="sxs-lookup"><span data-stu-id="aa649-272">If open generics and instantiated elements apply the same policy type</span></span>

<span data-ttu-id="aa649-273">Im folgenden Beispiel wird `Dictionary<int,int>` die `Browse`-Richtlinie nur dann zugewiesen, wenn die Engine einen anderen Grund hat, ihm die `Browse`-Richtlinie zuzuweisen (was sonst das Standardverhalten wäre). In jeder anderen Instanziierung von <xref:System.Collections.Generic.Dictionary%602> sind alle Member durchsuchbar.</span><span class="sxs-lookup"><span data-stu-id="aa649-273">In the following example, `Dictionary<int,int>` is assigned the `Browse` policy only if the engine has another reason to give it the `Browse` policy (which would otherwise be the default behavior); every other instantiation of <xref:System.Collections.Generic.Dictionary%602> will have all of its members browsable.</span></span>

```xml
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
   <Application>
      <Assembly Name="DataClasses" Serialize="Required Public" >
         <Namespace Name="DataClasses.ViewModels" Serialize="All" />
      </Assembly>
      <Namespace Name="DataClasses.Generics" />
      <Type Name="Dictionary" Browse="All" />
      <TypeInstantiation Name="Dictionary"
                         Arguments="System.Int32,System.Int32" Browse="Auto" />
   </Application>
   <Library Name="DataClasses">
      <!-- any other elements -->
   </Library>
</Directives>
```

### <a name="how-policy-is-inferred"></a><span data-ttu-id="aa649-274">Wie die Richtlinie abgeleitet wird</span><span class="sxs-lookup"><span data-stu-id="aa649-274">How policy is inferred</span></span>

<span data-ttu-id="aa649-275">Jeder Richtlinientyp besitzt einen anderen Satz von Regeln, die bestimmen, wie sich das Vorhandensein dieses Richtlinientyps auf andere Konstrukte auswirkt.</span><span class="sxs-lookup"><span data-stu-id="aa649-275">Each policy type has a different set of rules that determine how the presence of that policy type affects other constructs.</span></span>

#### <a name="the-effect-of-browse-policy"></a><span data-ttu-id="aa649-276">Auswirkungen der Browse-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="aa649-276">The effect of Browse policy</span></span>

<span data-ttu-id="aa649-277">Die Anwendung der `Browse`-Richtlinie auf einen Typ bewirkt die folgenden Richtlinienänderungen:</span><span class="sxs-lookup"><span data-stu-id="aa649-277">Applying the `Browse` policy to a type involves the following policy changes:</span></span>

- <span data-ttu-id="aa649-278">Der Basistyp des Typs wird mit der `Browse`-Richtlinie markiert.</span><span class="sxs-lookup"><span data-stu-id="aa649-278">The base type of the type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="aa649-279">Wenn der Typ ein instanziierter generischer Typ ist, wird die nicht instanziierte Version des Typs mit der `Browse`-Richtlinie markiert.</span><span class="sxs-lookup"><span data-stu-id="aa649-279">If the type is an instantiated generic, the uninstantiated version of the type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="aa649-280">Wenn der Typ ein Delegat ist, wird die `Invoke`-Methode des Typs mit der `Dynamic`-Richtlinie markiert.</span><span class="sxs-lookup"><span data-stu-id="aa649-280">If the type is a delegate, the `Invoke` method on the type is marked with the `Dynamic` policy.</span></span>

- <span data-ttu-id="aa649-281">Jede Schnittstelle des Typs wird mit der `Browse`-Richtlinie markiert.</span><span class="sxs-lookup"><span data-stu-id="aa649-281">Each interface of the type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="aa649-282">Der Typ jedes Attributs, das auf den Typ angewendet wird, wird mit der `Browse`-Richtlinie markiert.</span><span class="sxs-lookup"><span data-stu-id="aa649-282">The type of each attribute applied to the type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="aa649-283">Wenn der Typ generisch ist, wird jeder Einschränkungstyp mit der `Browse`-Richtlinie markiert.</span><span class="sxs-lookup"><span data-stu-id="aa649-283">If the type is generic, each constraint type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="aa649-284">Wenn der Typ generisch ist, werden die Typen, über die der Typ instanziiert wird, mit der `Browse`-Richtlinie markiert.</span><span class="sxs-lookup"><span data-stu-id="aa649-284">If the type is generic, the types over which the type is instantiated are marked with the `Browse` policy.</span></span>

<span data-ttu-id="aa649-285">Die Anwendung der `Browse`-Richtlinie auf eine Methode bewirkt die folgenden Richtlinienänderungen:</span><span class="sxs-lookup"><span data-stu-id="aa649-285">Applying the `Browse` policy to a method involves the following policy changes:</span></span>

- <span data-ttu-id="aa649-286">Jeder Parametertyp der Methode wird mit der `Browse`-Richtlinie markiert.</span><span class="sxs-lookup"><span data-stu-id="aa649-286">Each parameter type of the method is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="aa649-287">Der Rückgabetyp der Methode wird mit der `Browse`-Richtlinie markiert.</span><span class="sxs-lookup"><span data-stu-id="aa649-287">The return type of the method is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="aa649-288">Der enthaltende Typ der Methode wird mit der `Browse`-Richtlinie markiert.</span><span class="sxs-lookup"><span data-stu-id="aa649-288">The containing type of the method is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="aa649-289">Wenn die Methode eine instanziierte generische Methode ist, wird die nicht instanziierte generische Methode mit der `Browse`-Richtlinie markiert.</span><span class="sxs-lookup"><span data-stu-id="aa649-289">If the method is an instantiated generic method, the uninstantiated generic method is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="aa649-290">Der Typ jedes Attributs, das auf die Methode angewendet wird, wird mit der `Browse`-Richtlinie markiert.</span><span class="sxs-lookup"><span data-stu-id="aa649-290">The type of each attribute applied to the method is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="aa649-291">Wenn die Methode generisch ist, wird jeder Einschränkungstyp mit der `Browse`-Richtlinie markiert.</span><span class="sxs-lookup"><span data-stu-id="aa649-291">If the method is generic, each constraint type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="aa649-292">Wenn die Methode generisch ist, werden die Typen, über die die Methode instanziiert wird, mit der `Browse`-Richtlinie markiert.</span><span class="sxs-lookup"><span data-stu-id="aa649-292">If the method is generic, the types over which the method is instantiated are marked with the `Browse` policy.</span></span>

<span data-ttu-id="aa649-293">Die Anwendung der `Browse`-Richtlinie auf ein Feld bewirkt die folgenden Richtlinienänderungen:</span><span class="sxs-lookup"><span data-stu-id="aa649-293">Applying the `Browse` policy to a field involves the following policy changes:</span></span>

- <span data-ttu-id="aa649-294">Der Typ jedes Attributs, das auf das Feld angewendet wird, wird mit der `Browse`-Richtlinie markiert.</span><span class="sxs-lookup"><span data-stu-id="aa649-294">The type of each attribute applied to the field is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="aa649-295">Der Typ des Felds wird mit der `Browse`-Richtlinie markiert.</span><span class="sxs-lookup"><span data-stu-id="aa649-295">The type of the field is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="aa649-296">Der Typ, dem das Feld angehört, wird mit der `Browse`-Richtlinie markiert.</span><span class="sxs-lookup"><span data-stu-id="aa649-296">The type to which the field belongs is marked with the `Browse` policy.</span></span>

#### <a name="the-effect-of-dynamic-policy"></a><span data-ttu-id="aa649-297">Auswirkungen der Dynamic-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="aa649-297">The effect of Dynamic policy</span></span>

<span data-ttu-id="aa649-298">Die Anwendung der `Dynamic`-Richtlinie auf einen Typ bewirkt die folgenden Richtlinienänderungen:</span><span class="sxs-lookup"><span data-stu-id="aa649-298">Applying the `Dynamic` policy to a type involves the following policy changes:</span></span>

- <span data-ttu-id="aa649-299">Der Basistyp des Typs wird mit der `Dynamic`-Richtlinie markiert.</span><span class="sxs-lookup"><span data-stu-id="aa649-299">The base type of the type is marked with the `Dynamic` policy.</span></span>

- <span data-ttu-id="aa649-300">Wenn der Typ ein instanziierter generischer Typ ist, wird die nicht instanziierte Version des Typs mit der `Dynamic`-Richtlinie markiert.</span><span class="sxs-lookup"><span data-stu-id="aa649-300">If the type is an instantiated generic, the uninstantiated version of the type is marked with the `Dynamic` policy.</span></span>

- <span data-ttu-id="aa649-301">Wenn der Typ ein Delegattyp ist, wird die `Invoke`-Methode des Typs mit der `Dynamic`-Richtlinie markiert.</span><span class="sxs-lookup"><span data-stu-id="aa649-301">If the type is a delegate type, the `Invoke` method on the type is marked with the `Dynamic` policy.</span></span>

- <span data-ttu-id="aa649-302">Jede Schnittstelle des Typs wird mit der `Browse`-Richtlinie markiert.</span><span class="sxs-lookup"><span data-stu-id="aa649-302">Each interface of the type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="aa649-303">Der Typ jedes Attributs, das auf den Typ angewendet wird, wird mit der `Browse`-Richtlinie markiert.</span><span class="sxs-lookup"><span data-stu-id="aa649-303">The type of each attribute applied to the type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="aa649-304">Wenn der Typ generisch ist, wird jeder Einschränkungstyp mit der `Browse`-Richtlinie markiert.</span><span class="sxs-lookup"><span data-stu-id="aa649-304">If the type is generic, each constraint type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="aa649-305">Wenn der Typ generisch ist, werden die Typen, über die der Typ instanziiert wird, mit der `Browse`-Richtlinie markiert.</span><span class="sxs-lookup"><span data-stu-id="aa649-305">If the type is generic, the types over which the type is instantiated are marked with the `Browse` policy.</span></span>

<span data-ttu-id="aa649-306">Die Anwendung der `Dynamic`-Richtlinie auf eine Methode bewirkt die folgenden Richtlinienänderungen:</span><span class="sxs-lookup"><span data-stu-id="aa649-306">Applying the `Dynamic` policy to a method involves the following policy changes:</span></span>

- <span data-ttu-id="aa649-307">Jeder Parametertyp der Methode wird mit der `Browse`-Richtlinie markiert.</span><span class="sxs-lookup"><span data-stu-id="aa649-307">Each parameter type of the method is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="aa649-308">Der Rückgabetyp der Methode wird mit der `Dynamic`-Richtlinie markiert.</span><span class="sxs-lookup"><span data-stu-id="aa649-308">The return type of the method is marked with the `Dynamic` policy.</span></span>

- <span data-ttu-id="aa649-309">Der enthaltende Typ der Methode wird mit der `Dynamic`-Richtlinie markiert.</span><span class="sxs-lookup"><span data-stu-id="aa649-309">The containing type of the method is marked with the `Dynamic` policy.</span></span>

- <span data-ttu-id="aa649-310">Wenn die Methode eine instanziierte generische Methode ist, wird die nicht instanziierte generische Methode mit der `Browse`-Richtlinie markiert.</span><span class="sxs-lookup"><span data-stu-id="aa649-310">If the method is an instantiated generic method, the uninstantiated generic method is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="aa649-311">Der Typ jedes Attributs, das auf die Methode angewendet wird, wird mit der `Browse`-Richtlinie markiert.</span><span class="sxs-lookup"><span data-stu-id="aa649-311">The type of each attribute applied to the method is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="aa649-312">Wenn die Methode generisch ist, wird jeder Einschränkungstyp mit der `Browse`-Richtlinie markiert.</span><span class="sxs-lookup"><span data-stu-id="aa649-312">If the method is generic, each constraint type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="aa649-313">Wenn die Methode generisch ist, werden die Typen, über die die Methode instanziiert wird, mit der `Browse`-Richtlinie markiert.</span><span class="sxs-lookup"><span data-stu-id="aa649-313">If the method is generic, the types over which the method is instantiated are marked with the `Browse` policy.</span></span>

- <span data-ttu-id="aa649-314">Die Methode kann durch `MethodInfo.Invoke` aufgerufen werden, und Delegaterstellung wird möglich durch <xref:System.Reflection.MethodInfo.CreateDelegate%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="aa649-314">The method can be invoked by `MethodInfo.Invoke`, and delegate creation becomes possible by <xref:System.Reflection.MethodInfo.CreateDelegate%2A?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="aa649-315">Die Anwendung der `Dynamic`-Richtlinie auf ein Feld bewirkt die folgenden Richtlinienänderungen:</span><span class="sxs-lookup"><span data-stu-id="aa649-315">Applying the `Dynamic` policy to a field involves the following policy changes:</span></span>

- <span data-ttu-id="aa649-316">Der Typ jedes Attributs, das auf das Feld angewendet wird, wird mit der `Browse`-Richtlinie markiert.</span><span class="sxs-lookup"><span data-stu-id="aa649-316">The type of each attribute applied to the field is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="aa649-317">Der Typ des Felds wird mit der `Dynamic`-Richtlinie markiert.</span><span class="sxs-lookup"><span data-stu-id="aa649-317">The type of the field is marked with the `Dynamic` policy.</span></span>

- <span data-ttu-id="aa649-318">Der Typ, dem das Feld angehört, wird mit der `Dynamic`-Richtlinie markiert.</span><span class="sxs-lookup"><span data-stu-id="aa649-318">The type to which the field belongs is marked with the `Dynamic` policy.</span></span>

#### <a name="the-effect-of-activation-policy"></a><span data-ttu-id="aa649-319">Auswirkungen der Activation-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="aa649-319">The effect of Activation policy</span></span>

<span data-ttu-id="aa649-320">Die Anwendung der Activation-Richtlinie auf einen Typ bewirkt die folgenden Richtlinienänderungen:</span><span class="sxs-lookup"><span data-stu-id="aa649-320">Applying the Activation policy to a type involves the following policy changes:</span></span>

- <span data-ttu-id="aa649-321">Wenn der Typ ein instanziierter generischer Typ ist, wird die nicht instanziierte Version des Typs mit der `Browse`-Richtlinie markiert.</span><span class="sxs-lookup"><span data-stu-id="aa649-321">If the type is an instantiated generic, the uninstantiated version of the type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="aa649-322">Wenn der Typ ein Delegattyp ist, wird die `Invoke`-Methode des Typs mit der `Dynamic`-Richtlinie markiert.</span><span class="sxs-lookup"><span data-stu-id="aa649-322">If the type is a delegate type, the `Invoke` method on the type is marked with the `Dynamic` policy.</span></span>

- <span data-ttu-id="aa649-323">Konstruktoren des Typs werden mit der `Activation`-Richtlinie markiert.</span><span class="sxs-lookup"><span data-stu-id="aa649-323">Constructors of the type are marked with the `Activation` policy.</span></span>

<span data-ttu-id="aa649-324">Die Anwendung der `Activation`-Richtlinie auf eine Methode bewirkt die folgende Richtlinienänderung:</span><span class="sxs-lookup"><span data-stu-id="aa649-324">Applying the `Activation` policy to a method involves the following policy change:</span></span>

- <span data-ttu-id="aa649-325">Der Konstruktor kann durch die Methoden <xref:System.Reflection.ConstructorInfo.Invoke%2A?displayProperty=nameWithType> und <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType> aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="aa649-325">The constructor can be invoked by the <xref:System.Reflection.ConstructorInfo.Invoke%2A?displayProperty=nameWithType> and <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="aa649-326">Für Methoden betrifft die `Activation`-Richtlinie nur Konstruktoren.</span><span class="sxs-lookup"><span data-stu-id="aa649-326">For methods, the `Activation` policy affects constructors only.</span></span>

<span data-ttu-id="aa649-327">Die Anwendung der `Activation`-Richtlinie auf ein Feld hat keine Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="aa649-327">Applying the `Activation` policy to a field has no effect.</span></span>

#### <a name="the-effect-of-serialize-policy"></a><span data-ttu-id="aa649-328">Auswirkungen der Serialize-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="aa649-328">The effect of Serialize policy</span></span>

<span data-ttu-id="aa649-329">Die `Serialize`-Richtlinie ermöglicht die Verwendung gängiger reflektionsbasierter Serialisierungsprogramme.</span><span class="sxs-lookup"><span data-stu-id="aa649-329">The `Serialize` policy enables the use of common reflection-based serializers.</span></span> <span data-ttu-id="aa649-330">Aber da die genauen Reflektionszugriffsmuster von Nicht-Microsoft-Serialisierungsprogrammen Microsoft nicht bekannt sind, ist diese Richtlinie möglicherweise nicht ganz effektiv.</span><span class="sxs-lookup"><span data-stu-id="aa649-330">However, because the exact reflection access patterns of non-Microsoft serializers are not known to Microsoft, this policy may not be entirely effective.</span></span>

<span data-ttu-id="aa649-331">Die Anwendung der `Serialize`-Richtlinie auf einen Typ bewirkt die folgenden Richtlinienänderungen:</span><span class="sxs-lookup"><span data-stu-id="aa649-331">Applying the `Serialize` policy to a type involves the following policy changes:</span></span>

- <span data-ttu-id="aa649-332">Der Basistyp des Typs wird mit der `Serialize`-Richtlinie markiert.</span><span class="sxs-lookup"><span data-stu-id="aa649-332">The base type of the type is marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="aa649-333">Wenn der Typ ein instanziierter generischer Typ ist, wird die nicht instanziierte Version des Typs mit der `Browse`-Richtlinie markiert.</span><span class="sxs-lookup"><span data-stu-id="aa649-333">If the type is an instantiated generic, the uninstantiated version of the type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="aa649-334">Wenn der Typ ein Delegattyp ist, wird die `Invoke`-Methode des Typs mit der `Dynamic`-Richtlinie markiert.</span><span class="sxs-lookup"><span data-stu-id="aa649-334">If the type is a delegate type, the `Invoke` method on the type is marked with the `Dynamic` policy.</span></span>

- <span data-ttu-id="aa649-335">Wenn der Typ eine Enumeration ist, wird ein Array dieses Typs mit der `Serialize`-Richtlinie markiert.</span><span class="sxs-lookup"><span data-stu-id="aa649-335">If the type is an enumeration, an array of the type is marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="aa649-336">Wenn der Typ <xref:System.Collections.Generic.IEnumerable%601> implementiert, wird `T` mit der `Serialize`-Richtlinie markiert.</span><span class="sxs-lookup"><span data-stu-id="aa649-336">If the type implements <xref:System.Collections.Generic.IEnumerable%601>, `T` is marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="aa649-337">Wenn der Typ <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.Generic.IList%601>, <xref:System.Collections.Generic.ICollection%601>, <xref:System.Collections.Generic.IReadOnlyCollection%601> oder <xref:System.Collections.Generic.IReadOnlyList%601> ist, werden `T[]` und <xref:System.Collections.Generic.List%601> mit der `Serialize`-Richtlinie markiert, aber keine Member des Schnittstellentyps werden mit der `Serialize`-Richtlinie markiert.</span><span class="sxs-lookup"><span data-stu-id="aa649-337">If the type is <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.Generic.IList%601>, <xref:System.Collections.Generic.ICollection%601>, <xref:System.Collections.Generic.IReadOnlyCollection%601>, or <xref:System.Collections.Generic.IReadOnlyList%601>, then `T[]` and <xref:System.Collections.Generic.List%601> marked with the `Serialize` policy., but no members of the interface type are marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="aa649-338">Wenn der Typ <xref:System.Collections.Generic.List%601> ist, werden keine Member dieses Typs mit der `Serialize`-Richtlinie markiert.</span><span class="sxs-lookup"><span data-stu-id="aa649-338">If the type is <xref:System.Collections.Generic.List%601>, no members of the type are marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="aa649-339">Wenn der Typ <xref:System.Collections.Generic.IDictionary%602> ist, wird <xref:System.Collections.Generic.Dictionary%602> mit der `Serialize`-Richtlinie markiert.</span><span class="sxs-lookup"><span data-stu-id="aa649-339">If the type is <xref:System.Collections.Generic.IDictionary%602>, <xref:System.Collections.Generic.Dictionary%602> is marked with the `Serialize` policy.</span></span> <span data-ttu-id="aa649-340">aber keine Member des Typs werden mit der `Serialize`-Richtlinie markiert.</span><span class="sxs-lookup"><span data-stu-id="aa649-340">but no members of the type are marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="aa649-341">Wenn der Typ <xref:System.Collections.Generic.Dictionary%602> ist, werden keine Member dieses Typs mit der `Serialize`-Richtlinie markiert.</span><span class="sxs-lookup"><span data-stu-id="aa649-341">If the type is <xref:System.Collections.Generic.Dictionary%602>, no members of the type are marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="aa649-342">Wenn der Typ <xref:System.Collections.Generic.IDictionary%602> implementiert, werden `TKey` und `TValue` mit der `Serialize`-Richtlinie markiert.</span><span class="sxs-lookup"><span data-stu-id="aa649-342">If the type implements <xref:System.Collections.Generic.IDictionary%602>, `TKey` and `TValue` are marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="aa649-343">Jeder Konstruktor, jede Eigenschaftenzugriffsmethode und jedes Feld wird mit der `Serialize`-Richtlinie markiert.</span><span class="sxs-lookup"><span data-stu-id="aa649-343">Each constructor, each property accessor, and each field is marked with the `Serialize` policy.</span></span>

<span data-ttu-id="aa649-344">Die Anwendung der `Serialize`-Richtlinie auf eine Methode bewirkt die folgenden Richtlinienänderungen:</span><span class="sxs-lookup"><span data-stu-id="aa649-344">Applying the `Serialize` policy to a method involves the following policy changes:</span></span>

- <span data-ttu-id="aa649-345">Der enthaltende Typ wird mit der `Serialize`-Richtlinie markiert.</span><span class="sxs-lookup"><span data-stu-id="aa649-345">The containing type is marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="aa649-346">Der Rückgabetyp der Methode wird mit der `Serialize`-Richtlinie markiert.</span><span class="sxs-lookup"><span data-stu-id="aa649-346">The return type of the method is marked with the `Serialize` policy.</span></span>

<span data-ttu-id="aa649-347">Die Anwendung der `Serialize`-Richtlinie auf ein Feld bewirkt die folgenden Richtlinienänderungen:</span><span class="sxs-lookup"><span data-stu-id="aa649-347">Applying the `Serialize` policy to a field involves the following policy changes:</span></span>

- <span data-ttu-id="aa649-348">Der enthaltende Typ wird mit der `Serialize`-Richtlinie markiert.</span><span class="sxs-lookup"><span data-stu-id="aa649-348">The containing type is marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="aa649-349">Der Typ des Felds wird mit der `Serialize`-Richtlinie markiert.</span><span class="sxs-lookup"><span data-stu-id="aa649-349">The type of the field is marked with the `Serialize` policy.</span></span>

#### <a name="the-effect-of-xmlserializer-datacontractserializer-and-datacontractjsonserializer-policies"></a><span data-ttu-id="aa649-350">Die Auswirkungen der Richtlinien XmlSerializer, DataContractSerializer und DataContractJsonSerializer</span><span class="sxs-lookup"><span data-stu-id="aa649-350">The effect of XmlSerializer, DataContractSerializer, and DataContractJsonSerializer policies</span></span>

<span data-ttu-id="aa649-351">Anders als bei der `Serialize` Richtlinie, die für reflektionsbasierte Serialisierungstypen gedacht ist, werden die Richtlinien für die <xref:System.Xml.Serialization.XmlSerializer>, <xref:System.Runtime.Serialization.DataContractSerializer>und <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> verwendet, um eine Reihe von Serialisierern zu aktivieren, die der .net Native-Toolkette bekannt sind.</span><span class="sxs-lookup"><span data-stu-id="aa649-351">Unlike the `Serialize` policy, which is intended for reflection-based serializers, the <xref:System.Xml.Serialization.XmlSerializer>, <xref:System.Runtime.Serialization.DataContractSerializer>, and <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> policies are used to enable a set of serializers that are known to the .NET Native tool chain.</span></span> <span data-ttu-id="aa649-352">Diese Serialisierungsprogramme werden nicht mithilfe von Reflektion implementiert, aber der Satz von Typen, die zur Laufzeit serialisiert werden können, wird auf ähnliche Weise wie reflektierbare Typen bestimmt.</span><span class="sxs-lookup"><span data-stu-id="aa649-352">These serializers are not implemented by using reflection, but the set of types that can be serialized at run time is determined in a similar manner as types that are reflectable.</span></span>

<span data-ttu-id="aa649-353">Die Anwendung einer dieser Richtlinien auf einen Typ ermöglicht die Serialisierung des Typs mit dem entsprechenden Serialisierungsprogramm.</span><span class="sxs-lookup"><span data-stu-id="aa649-353">Applying one of these policies to a type enables the type to be serialized with the matching serializer.</span></span> <span data-ttu-id="aa649-354">Außerdem können alle Typen, von denen die Serialisierungs-Engine statisch bestimmen kann, dass für sie Serialisierung erforderlich ist, serialisierbar sein.</span><span class="sxs-lookup"><span data-stu-id="aa649-354">Also, any types that the serialization engine can statically determine as needing serialization will also be serializable.</span></span>

<span data-ttu-id="aa649-355">Diese Richtlinien wirken sich nicht auf Methoden oder Felder aus.</span><span class="sxs-lookup"><span data-stu-id="aa649-355">These policies have no effect on methods or fields.</span></span>

<span data-ttu-id="aa649-356">Weitere Informationen finden Sie im Abschnitt „Unterschiede in den Serialisierungsprogrammen“ [Migrieren Ihrer Windows Store-App auf .NET Native](migrating-your-windows-store-app-to-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="aa649-356">For more information, see the "Differences in Serializers" section in [Migrating Your Windows Store App to .NET Native](migrating-your-windows-store-app-to-net-native.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="aa649-357">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aa649-357">See also</span></span>

- [<span data-ttu-id="aa649-358">Elemente der Laufzeitanweisung</span><span class="sxs-lookup"><span data-stu-id="aa649-358">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
- [<span data-ttu-id="aa649-359">Reflection and .NET Native (Reflektion und .NET Native)</span><span class="sxs-lookup"><span data-stu-id="aa649-359">Reflection and .NET Native</span></span>](reflection-and-net-native.md)

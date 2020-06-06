---
title: <Library>-Element (.net Native)
ms.date: 03/30/2017
ms.assetid: f642276b-33fb-4a81-b882-8808c31ba69e
ms.openlocfilehash: f94bfe047fa7a95b6f24264bae0b27112c589dfd
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "73128369"
---
# <a name="library-element-net-native"></a><span data-ttu-id="a29f2-102">\<Library>-Element (.net Native)</span><span class="sxs-lookup"><span data-stu-id="a29f2-102">\<Library> Element (.NET Native)</span></span>
<span data-ttu-id="a29f2-103">Definiert die Assembly, die Typen und Typmember enthält, deren Metadaten zur Laufzeit für die Reflektion verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="a29f2-103">Defines the assembly that contains types and type members whose metadata is available for reflection at run time.</span></span>  
  
 <span data-ttu-id="a29f2-104">\<Directives>-Element</span><span class="sxs-lookup"><span data-stu-id="a29f2-104">\<Directives> Element</span></span>  
<span data-ttu-id="a29f2-105">\<Library>-Element</span><span class="sxs-lookup"><span data-stu-id="a29f2-105">\<Library> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a29f2-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="a29f2-106">Syntax</span></span>  
  
```xml  
<Library Name="assembly_name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a29f2-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a29f2-107">Attributes and Elements</span></span>  
 <span data-ttu-id="a29f2-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a29f2-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a29f2-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="a29f2-109">Attributes</span></span>  
  
|<span data-ttu-id="a29f2-110">attribute</span><span class="sxs-lookup"><span data-stu-id="a29f2-110">Attribute</span></span>|<span data-ttu-id="a29f2-111">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="a29f2-111">Description</span></span>|  
|---------------|-----------------|  
|`Name`|<span data-ttu-id="a29f2-112">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="a29f2-112">Required attribute.</span></span> <span data-ttu-id="a29f2-113">Gibt den Namen einer Assembly an.</span><span class="sxs-lookup"><span data-stu-id="a29f2-113">Specifies the name of an assembly.</span></span> <span data-ttu-id="a29f2-114">Untergeordnete Elemente dieses `<Library>`-Elements definieren die Laufzeitreflektionsrichtlinie für Typen und Typmember in dieser Assembly.</span><span class="sxs-lookup"><span data-stu-id="a29f2-114">Child elements of this `<Library>` element define the runtime reflection policy for types and type members found in this assembly.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="a29f2-115">Namensattribut</span><span class="sxs-lookup"><span data-stu-id="a29f2-115">Name attribute</span></span>  
  
|<span data-ttu-id="a29f2-116">Wert</span><span class="sxs-lookup"><span data-stu-id="a29f2-116">Value</span></span>|<span data-ttu-id="a29f2-117">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="a29f2-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a29f2-118">*assembly_name*</span><span class="sxs-lookup"><span data-stu-id="a29f2-118">*assembly_name*</span></span>|<span data-ttu-id="a29f2-119">Der einfache Name der Assembly ohne Dateierweiterung.</span><span class="sxs-lookup"><span data-stu-id="a29f2-119">The simple name of the assembly, without its file extension.</span></span> <span data-ttu-id="a29f2-120">Dieses Attribut entspricht der <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType>-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="a29f2-120">This attribute corresponds to the <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="a29f2-121">Der Name einer Assembly namens Extensions.dll lautet beispielsweise "Extensions".</span><span class="sxs-lookup"><span data-stu-id="a29f2-121">For example, the name of an assembly named Extensions.dll is "Extensions".</span></span> <span data-ttu-id="a29f2-122">Im Abschnitt „Hinweise“ ist eine besondere Form von *assembly_name* beschrieben, die den bedingten Einschluss von Metadaten aus der Assembly unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a29f2-122">See the Remarks section for a special form of *assembly_name* that supports conditional inclusion of metadata from the assembly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a29f2-123">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a29f2-123">Child Elements</span></span>  
  
|<span data-ttu-id="a29f2-124">Element</span><span class="sxs-lookup"><span data-stu-id="a29f2-124">Element</span></span>|<span data-ttu-id="a29f2-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a29f2-125">Description</span></span>|  
|-------------|-----------------|  
|[\<Assembly>](assembly-element-net-native.md)|<span data-ttu-id="a29f2-126">Wendet die Richtlinie auf alle Typen in einer bestimmten Assembly an.</span><span class="sxs-lookup"><span data-stu-id="a29f2-126">Applies policy to all the types in a particular assembly.</span></span>|  
|[\<Namespace>](namespace-element-net-native.md)|<span data-ttu-id="a29f2-127">Wendet die Richtlinie auf alle Typen in einem bestimmten Namespace an.</span><span class="sxs-lookup"><span data-stu-id="a29f2-127">Applies policy to all the types in a particular namespace.</span></span>|  
|[\<Type>](type-element-net-native.md)|<span data-ttu-id="a29f2-128">Wendet die Richtlinie auf einen bestimmten Typ, z. B. eine Klasse oder Struktur, an.</span><span class="sxs-lookup"><span data-stu-id="a29f2-128">Applies policy to a particular type, such as a class or structure.</span></span>|  
|[\<TypeInstantiation>](typeinstantiation-element-net-native.md)|<span data-ttu-id="a29f2-129">Wendet die Richtlinie auf einen konstruierten generischen Typ an.</span><span class="sxs-lookup"><span data-stu-id="a29f2-129">Applies policy to a constructed generic type.</span></span> <span data-ttu-id="a29f2-130">Beispielsweise kann ein- [\<TypeInstantiation>](typeinstantiation-element-net-native.md) Element verwendet werden, um Richtlinien für einen Typ zu definieren `List<String>` .</span><span class="sxs-lookup"><span data-stu-id="a29f2-130">For example, a [\<TypeInstantiation>](typeinstantiation-element-net-native.md) element could be used to define policy for a `List<String>` type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a29f2-131">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a29f2-131">Parent Elements</span></span>  
  
|<span data-ttu-id="a29f2-132">Element</span><span class="sxs-lookup"><span data-stu-id="a29f2-132">Element</span></span>|<span data-ttu-id="a29f2-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a29f2-133">Description</span></span>|  
|-------------|-----------------|  
|[\<Directives>](directives-element-net-native.md)|<span data-ttu-id="a29f2-134">Das Stammelement einer Laufzeitanweisungsdatei.</span><span class="sxs-lookup"><span data-stu-id="a29f2-134">The root element of a runtime directives file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a29f2-135">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="a29f2-135">Remarks</span></span>  
 <span data-ttu-id="a29f2-136">Das- [\<Directives>](directives-element-net-native.md) Element kann NULL, ein oder mehrere- `<Library>` Elemente enthalten.</span><span class="sxs-lookup"><span data-stu-id="a29f2-136">The [\<Directives>](directives-element-net-native.md) element can contain zero, one, or more `<Library>` elements.</span></span>  
  
 <span data-ttu-id="a29f2-137">Das `<Library>`-Element dient als Container für die Definition der Programmelemente, deren Metadaten zur Laufzeit benötigt werden. Dieses Element drückt keine Richtlinie aus.</span><span class="sxs-lookup"><span data-stu-id="a29f2-137">The `<Library>` element serves as a container to define the program elements whose metadata is needed at run time; this element doesn't express policy.</span></span> <span data-ttu-id="a29f2-138">Zur Kompilierzeit durchsuchen die Compilertools nur die im `<Library>`-Element bezeichnete Bibliothek nach Programmelementen, die durch seine untergeordneten Elemente identifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="a29f2-138">At compile time, compiler tools search only the library designated by the `<Library>` element for program elements identified by its child elements.</span></span> <span data-ttu-id="a29f2-139">Im Gegensatz dazu durchsuchen Compilertools alle Bibliotheken, including.NET Framework-Kernbibliotheken, nach Programmelementen, die durch untergeordnete Elemente des-Elements identifiziert werden [\<Application>](application-element-net-native.md) .</span><span class="sxs-lookup"><span data-stu-id="a29f2-139">In contrast, compiler tools search all libraries, including.NET Framework core libraries, for program elements identified by child elements of the [\<Application>](application-element-net-native.md) element.</span></span>  
  
 <span data-ttu-id="a29f2-140">`<Library>`-Direktiven können bedingt verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a29f2-140">`<Library>` directives may be conditionally utilized.</span></span> <span data-ttu-id="a29f2-141">Wenn der Name des `<Library>` Elements mit einem Sternchen () beginnt und endet \* , wirkt sich die `<Library>` Direktive nur dann aus, wenn die APP auf die zwischen den Sternchen angegebene Assembly verweist.</span><span class="sxs-lookup"><span data-stu-id="a29f2-141">If the name of the `<Library>` element starts and ends with an asterisk (\*), the `<Library>` directive has an effect only if the assembly specified between the asterisks is referenced by the app.</span></span> <span data-ttu-id="a29f2-142">Beispielsweise gilt die folgende Lauf Zeit Direktive nur, wenn von der APP auf die Assembly Utilities. dll verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="a29f2-142">For example, the following runtime directive applies only if the Utilities.dll assembly is referenced by the app.</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
  <Library Name="*Utilities*">  
   ...  
  </Library>  
</Directives>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a29f2-143">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a29f2-143">See also</span></span>

- [<span data-ttu-id="a29f2-144">\<Application>Gewisses</span><span class="sxs-lookup"><span data-stu-id="a29f2-144">\<Application> Element</span></span>](application-element-net-native.md)
- [<span data-ttu-id="a29f2-145">\<Directives>Gewisses</span><span class="sxs-lookup"><span data-stu-id="a29f2-145">\<Directives> Element</span></span>](directives-element-net-native.md)
- [<span data-ttu-id="a29f2-146">Laufzeitanweisungs-Konfigurationsdatei (rd.xml) Referenz</span><span class="sxs-lookup"><span data-stu-id="a29f2-146">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="a29f2-147">Elemente der Laufzeitanweisung</span><span class="sxs-lookup"><span data-stu-id="a29f2-147">Runtime Directive Elements</span></span>](runtime-directive-elements.md)

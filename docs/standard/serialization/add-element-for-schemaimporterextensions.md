---
title: '&lt;Hinzufügen&gt; -Element für &lt;SchemaImporterExtensions&gt;'
ms.date: 03/30/2017
helpviewer_keywords:
- XML serialization, configuration
- <add> element for <schemaImporterExtensions> element
ms.assetid: c828a558-094b-441e-9065-790b87315fa0
ms.openlocfilehash: 3d3c72fd64042032d44c49ebde867d111ce03b94
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2018
ms.locfileid: "42936600"
---
# <a name="ltaddgt-element-for-ltschemaimporterextensionsgt"></a><span data-ttu-id="d47af-102">&lt;Hinzufügen&gt; -Element für &lt;SchemaImporterExtensions&gt;</span><span class="sxs-lookup"><span data-stu-id="d47af-102">&lt;add&gt; Element for &lt;schemaImporterExtensions&gt;</span></span>
<span data-ttu-id="d47af-103">Fügt Typen hinzu, die von <xref:System.Xml.Serialization.XmlSchemaImporter> verwendet werden, um XSD-Typen .NET Framework-Typen zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="d47af-103">Adds types used by the <xref:System.Xml.Serialization.XmlSchemaImporter> for mapping XSD types to .NET Framework types.</span></span> <span data-ttu-id="d47af-104">Weitere Informationen zu Konfigurationsdateien finden Sie unter [Konfigurationsdateienschema](../../../docs/framework/configure-apps/file-schema/index.md).</span><span class="sxs-lookup"><span data-stu-id="d47af-104">For more information about configuration files, see [Configuration File Schema](../../../docs/framework/configure-apps/file-schema/index.md).</span></span>  
  
 <span data-ttu-id="d47af-105">\<configuration></span><span class="sxs-lookup"><span data-stu-id="d47af-105">\<configuration></span></span>  
<span data-ttu-id="d47af-106">\<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="d47af-106">\<system.xml.serialization></span></span>  
<span data-ttu-id="d47af-107">\<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="d47af-107">\<schemaImporterExtensions></span></span>  
<span data-ttu-id="d47af-108">\<add></span><span class="sxs-lookup"><span data-stu-id="d47af-108">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d47af-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="d47af-109">Syntax</span></span>  
  
```xml  
<add name = "typeName" type="fully qualified type [,Version=version number] [,Culture=culture] [,PublicKeyToken= token]"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d47af-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="d47af-110">Attributes and Elements</span></span>  
 <span data-ttu-id="d47af-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d47af-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d47af-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="d47af-112">Attributes</span></span>  
  
|<span data-ttu-id="d47af-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="d47af-113">Attribute</span></span>|<span data-ttu-id="d47af-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d47af-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d47af-115">**name**</span><span class="sxs-lookup"><span data-stu-id="d47af-115">**name**</span></span>|<span data-ttu-id="d47af-116">Ein einfacher Name, der zum Suchen der Instanz verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d47af-116">A simple name that is used to find the instance.</span></span>|  
|<span data-ttu-id="d47af-117">**Typ**</span><span class="sxs-lookup"><span data-stu-id="d47af-117">**type**</span></span>|<span data-ttu-id="d47af-118">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d47af-118">Required.</span></span> <span data-ttu-id="d47af-119">Gibt die Schemaerweiterungsklasse an, die hinzugefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="d47af-119">Specifies the schema  extension class to add.</span></span> <span data-ttu-id="d47af-120">Der Wert des **type**-Attributs muss sich in einer Zeile befinden und schließt den vollständigen Typnamen enthalten.</span><span class="sxs-lookup"><span data-stu-id="d47af-120">The **type** attribute value must be on one line, and include the fully qualified type name.</span></span> <span data-ttu-id="d47af-121">Wenn die Assembly im globalen Assemblycache (GAC) gespeichert ist, muss außerdem die Version, die Kultur und das Token des öffentlichen Schlüssels der signierten Assembly enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="d47af-121">When the assembly is placed in the Global Assembly Cache (GAC), it must also include the version, culture, and public key token of the signed assembly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d47af-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d47af-122">Child Elements</span></span>  
 <span data-ttu-id="d47af-123">Keine</span><span class="sxs-lookup"><span data-stu-id="d47af-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d47af-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d47af-124">Parent Elements</span></span>  
  
|<span data-ttu-id="d47af-125">Element</span><span class="sxs-lookup"><span data-stu-id="d47af-125">Element</span></span>|<span data-ttu-id="d47af-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d47af-126">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d47af-127">\<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="d47af-127">\<schemaImporterExtensions></span></span>|<span data-ttu-id="d47af-128">Enthält die Typen, die von der <xref:System.Xml.Serialization.XmlSchemaImporter>-Klasse verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d47af-128">Contains the types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter>.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d47af-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d47af-129">Example</span></span>  
 <span data-ttu-id="d47af-130">Im folgenden Codebeispiel wird ein Erweiterungstyp hinzugefügt, den XmlSchemaImporter zum Zuordnen von Typen verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="d47af-130">The following code example adds an extension type that the XmlSchemaImporter can use when mapping types.</span></span>  
  
```xml  
<configuration>  
  <system.xml.serialization>  
    <schemaImporterExtensions>  
       <add name="contoso" type="System.Web.Mobile.MobileCapabilities,   
       System.Web.Mobile, Version=2.0.0.0, Culture=neutral,   
       PublicKeyToken=b03f5f7f11d50a3a" />   
    </schemaImporterExtensions>  
  </system.xml.serialization>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d47af-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d47af-131">See Also</span></span>  
 <xref:System.Xml.Serialization.XmlSchemaImporter>  
 [<span data-ttu-id="d47af-132">\<system.xml.serialization>-Element</span><span class="sxs-lookup"><span data-stu-id="d47af-132">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)  
 [<span data-ttu-id="d47af-133">\<schemaImporterExtensions>-Element</span><span class="sxs-lookup"><span data-stu-id="d47af-133">\<schemaImporterExtensions> Element</span></span>](../../../docs/standard/serialization/schemaimporterextensions-element.md)

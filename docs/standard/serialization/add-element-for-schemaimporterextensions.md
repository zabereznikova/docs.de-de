---
title: <add>-Element für <schemaImporterExtensions>
description: Das <add>-Element fügt Typen hinzu, mit denen die XmlSchemaImporter-Klasse XSD-Typen .NET Framework-Typen zuordnet.
ms.date: 03/30/2017
helpviewer_keywords:
- XML serialization, configuration
- <add> element for <schemaImporterExtensions> element
ms.assetid: c828a558-094b-441e-9065-790b87315fa0
ms.openlocfilehash: 401d1ba9cc2f97e93d7851f96f73b552e6ed6356
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378482"
---
# <a name="add-element-for-schemaimporterextensions"></a><span data-ttu-id="9159e-103">\<add>-Element für \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="9159e-103">\<add> Element for \<schemaImporterExtensions></span></span>
<span data-ttu-id="9159e-104">Fügt Typen hinzu, die von <xref:System.Xml.Serialization.XmlSchemaImporter> verwendet werden, um XSD-Typen .NET Framework-Typen zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="9159e-104">Adds types used by the <xref:System.Xml.Serialization.XmlSchemaImporter> for mapping XSD types to .NET Framework types.</span></span> <span data-ttu-id="9159e-105">Weitere Informationen zu Konfigurationsdateien finden Sie unter [Konfigurationsdateienschema](../../../docs/framework/configure-apps/file-schema/index.md).</span><span class="sxs-lookup"><span data-stu-id="9159e-105">For more information about configuration files, see [Configuration File Schema](../../../docs/framework/configure-apps/file-schema/index.md).</span></span>  
  
 <span data-ttu-id="9159e-106">\<configuration></span><span class="sxs-lookup"><span data-stu-id="9159e-106">\<configuration></span></span>  
<span data-ttu-id="9159e-107">\<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="9159e-107">\<system.xml.serialization></span></span>  
<span data-ttu-id="9159e-108">\<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="9159e-108">\<schemaImporterExtensions></span></span>  
<span data-ttu-id="9159e-109">\<add></span><span class="sxs-lookup"><span data-stu-id="9159e-109">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9159e-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="9159e-110">Syntax</span></span>  
  
```xml  
<add name = "typeName" type="fully qualified type [,Version=version number] [,Culture=culture] [,PublicKeyToken= token]"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9159e-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="9159e-111">Attributes and Elements</span></span>  
 <span data-ttu-id="9159e-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9159e-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9159e-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="9159e-113">Attributes</span></span>  
  
|<span data-ttu-id="9159e-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="9159e-114">Attribute</span></span>|<span data-ttu-id="9159e-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9159e-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9159e-116">**name**</span><span class="sxs-lookup"><span data-stu-id="9159e-116">**name**</span></span>|<span data-ttu-id="9159e-117">Ein einfacher Name, der zum Suchen der Instanz verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9159e-117">A simple name that is used to find the instance.</span></span>|  
|<span data-ttu-id="9159e-118">**Typ**</span><span class="sxs-lookup"><span data-stu-id="9159e-118">**type**</span></span>|<span data-ttu-id="9159e-119">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="9159e-119">Required.</span></span> <span data-ttu-id="9159e-120">Gibt die Schemaerweiterungsklasse an, die hinzugefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="9159e-120">Specifies the schema  extension class to add.</span></span> <span data-ttu-id="9159e-121">Der Wert des **type**-Attributs muss sich in einer Zeile befinden und schließt den vollständigen Typnamen enthalten.</span><span class="sxs-lookup"><span data-stu-id="9159e-121">The **type** attribute value must be on one line, and include the fully qualified type name.</span></span> <span data-ttu-id="9159e-122">Wenn die Assembly im globalen Assemblycache (GAC) gespeichert ist, muss außerdem die Version, die Kultur und das Token des öffentlichen Schlüssels der signierten Assembly enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="9159e-122">When the assembly is placed in the Global Assembly Cache (GAC), it must also include the version, culture, and public key token of the signed assembly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9159e-123">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9159e-123">Child Elements</span></span>  
 <span data-ttu-id="9159e-124">Keine</span><span class="sxs-lookup"><span data-stu-id="9159e-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9159e-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9159e-125">Parent Elements</span></span>  
  
|<span data-ttu-id="9159e-126">Element</span><span class="sxs-lookup"><span data-stu-id="9159e-126">Element</span></span>|<span data-ttu-id="9159e-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9159e-127">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9159e-128">\<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="9159e-128">\<schemaImporterExtensions></span></span>|<span data-ttu-id="9159e-129">Enthält die Typen, die von der <xref:System.Xml.Serialization.XmlSchemaImporter>-Klasse verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9159e-129">Contains the types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter>.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="9159e-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9159e-130">Example</span></span>  
 <span data-ttu-id="9159e-131">Im folgenden Codebeispiel wird ein Erweiterungstyp hinzugefügt, den XmlSchemaImporter zum Zuordnen von Typen verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="9159e-131">The following code example adds an extension type that the XmlSchemaImporter can use when mapping types.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9159e-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9159e-132">See also</span></span>

- <xref:System.Xml.Serialization.XmlSchemaImporter>
- [<span data-ttu-id="9159e-133">\<system.xml.serialization>-Element</span><span class="sxs-lookup"><span data-stu-id="9159e-133">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)
- [<span data-ttu-id="9159e-134">\<schemaImporterExtensions>-Element</span><span class="sxs-lookup"><span data-stu-id="9159e-134">\<schemaImporterExtensions> Element</span></span>](../../../docs/standard/serialization/schemaimporterextensions-element.md)

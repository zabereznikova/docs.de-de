---
title: "&lt;add&gt;-Element für &lt;xmlSchemaImporterExtensions&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XML serialization, configuration
- <add> element for <xmlSchemaImporterExtensions> element
ms.assetid: c828a558-094b-441e-9065-790b87315fa0
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: fd73d6dfe6659cd973054a14d0d4e5e73d3cd8d7
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="ltaddgt-element-for-ltxmlschemaimporterextensionsgt"></a><span data-ttu-id="2d158-102">&lt;add&gt;-Element für &lt;xmlSchemaImporterExtensions&gt;</span><span class="sxs-lookup"><span data-stu-id="2d158-102">&lt;add&gt; Element for &lt;xmlSchemaImporterExtensions&gt;</span></span>
<span data-ttu-id="2d158-103">Fügt Typen hinzu, die von <xref:System.Xml.Serialization.XmlSchemaImporter> verwendet werden, um XSD-Typen .NET Framework-Typen zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="2d158-103">Adds types used by the <xref:System.Xml.Serialization.XmlSchemaImporter> for mapping XSD types to .NET Framework types.</span></span> <span data-ttu-id="2d158-104">Weitere Informationen zu Konfigurationsdateien finden Sie unter [Konfigurationsdateienschema](../../../docs/framework/configure-apps/file-schema/index.md).</span><span class="sxs-lookup"><span data-stu-id="2d158-104">For more information about configuration files, see [Configuration File Schema](../../../docs/framework/configure-apps/file-schema/index.md).</span></span>  
  
 <span data-ttu-id="2d158-105">\<configuration></span><span class="sxs-lookup"><span data-stu-id="2d158-105">\<configuration></span></span>  
<span data-ttu-id="2d158-106">\<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="2d158-106">\<system.xml.serialization></span></span>  
<span data-ttu-id="2d158-107">\<XmlSchemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="2d158-107">\<XmlSchemaImporterExtensions></span></span>  
<span data-ttu-id="2d158-108">\<add></span><span class="sxs-lookup"><span data-stu-id="2d158-108">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d158-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="2d158-109">Syntax</span></span>  
  
```xml  
<add name = "typeName" type="fully qualified type [,Version=version number] [,Culture=culture] [,PublicKeyToken= token]"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2d158-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="2d158-110">Attributes and Elements</span></span>  
 <span data-ttu-id="2d158-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2d158-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2d158-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="2d158-112">Attributes</span></span>  
  
|<span data-ttu-id="2d158-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="2d158-113">Attribute</span></span>|<span data-ttu-id="2d158-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2d158-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2d158-115">**name**</span><span class="sxs-lookup"><span data-stu-id="2d158-115">**name**</span></span>|<span data-ttu-id="2d158-116">Ein einfacher Name, der zum Suchen der Instanz verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2d158-116">A simple name that is used to find the instance.</span></span>|  
|<span data-ttu-id="2d158-117">**Typ**</span><span class="sxs-lookup"><span data-stu-id="2d158-117">**type**</span></span>|<span data-ttu-id="2d158-118">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2d158-118">Required.</span></span> <span data-ttu-id="2d158-119">Gibt die Schemaerweiterungsklasse an, die hinzugefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="2d158-119">Specifies the schema  extension class to add.</span></span> <span data-ttu-id="2d158-120">Der Wert des **type**-Attributs muss sich in einer Zeile befinden und schließt den vollständigen Typnamen enthalten.</span><span class="sxs-lookup"><span data-stu-id="2d158-120">The **type** attribute value must be on one line, and include the fully qualified type name.</span></span> <span data-ttu-id="2d158-121">Wenn die Assembly im globalen Assemblycache (GAC) gespeichert ist, muss außerdem die Version, die Kultur und das Token des öffentlichen Schlüssels der signierten Assembly enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="2d158-121">When the assembly is placed in the Global Assembly Cache (GAC), it must also include the version, culture, and public key token of the signed assembly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2d158-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2d158-122">Child Elements</span></span>  
 <span data-ttu-id="2d158-123">Keine</span><span class="sxs-lookup"><span data-stu-id="2d158-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2d158-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2d158-124">Parent Elements</span></span>  
  
|<span data-ttu-id="2d158-125">Element</span><span class="sxs-lookup"><span data-stu-id="2d158-125">Element</span></span>|<span data-ttu-id="2d158-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2d158-126">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2d158-127">\<xmlSchemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="2d158-127">\<xmlSchemaImporterExtensions></span></span>|<span data-ttu-id="2d158-128">Enthält die Typen, die von der <xref:System.Xml.Serialization.XmlSchemaImporter>-Klasse verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2d158-128">Contains the types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter>.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="2d158-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2d158-129">Example</span></span>  
 <span data-ttu-id="2d158-130">Im folgenden Codebeispiel wird ein Erweiterungstyp hinzugefügt, den XmlSchemaImporter zum Zuordnen von Typen verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="2d158-130">The following code example adds an extension type that the XmlSchemaImporter can use when mapping types.</span></span>  
  
```xml  
<configuration>  
  <system.xml.serialization>  
    <xmlSchemaImporterExtensions>  
       <add name="contoso" type="System.Web.Mobile.MobileCapabilities,   
       System.Web.Mobile, Version=2.0.0.0, Culture=neutral,   
       PublicKeyToken=b03f5f7f11d50a3a" />   
    </xmlSchemaImporterExtensions>  
  </system.xml.serialization>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2d158-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2d158-131">See Also</span></span>  
 <xref:System.Xml.Serialization.XmlSchemaImporter>  
 [<span data-ttu-id="2d158-132">\<system.xml.serialization>-Element</span><span class="sxs-lookup"><span data-stu-id="2d158-132">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)  
 [<span data-ttu-id="2d158-133">\<schemaImporterExtensions>-Element</span><span class="sxs-lookup"><span data-stu-id="2d158-133">\<schemaImporterExtensions> Element</span></span>](../../../docs/standard/serialization/schemaimporterextensions-element.md)

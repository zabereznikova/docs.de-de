---
title: <add>-Element für <schemaImporterExtensions>
description: Das <add>-Element fügt Typen hinzu, mit denen die XmlSchemaImporter-Klasse XSD-Typen .NET-Typen zuordnet.
ms.date: 03/30/2017
helpviewer_keywords:
- XML serialization, configuration
- <add> element for <schemaImporterExtensions> element
ms.assetid: c828a558-094b-441e-9065-790b87315fa0
ms.openlocfilehash: b8a0775e9d33d59606b1150aa9a1b3b1026d4b0b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726443"
---
# <a name="add-element-for-schemaimporterextensions"></a><span data-ttu-id="34a5b-103">\<add>-Element für \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="34a5b-103">\<add> Element for \<schemaImporterExtensions></span></span>

<span data-ttu-id="34a5b-104">Fügt Typen hinzu, die von <xref:System.Xml.Serialization.XmlSchemaImporter> verwendet werden, um XSD-Typen .NET-Typen zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="34a5b-104">Adds types used by the <xref:System.Xml.Serialization.XmlSchemaImporter> for mapping XSD types to .NET types.</span></span> <span data-ttu-id="34a5b-105">Weitere Informationen zu Konfigurationsdateien finden Sie unter [Konfigurationsdateienschema](../../framework/configure-apps/file-schema/index.md).</span><span class="sxs-lookup"><span data-stu-id="34a5b-105">For more information about configuration files, see [Configuration File Schema](../../framework/configure-apps/file-schema/index.md).</span></span>  
  
\<configuration>  
\<system.xml.serialization>  
\<schemaImporterExtensions>  
\<add>  
  
## <a name="syntax"></a><span data-ttu-id="34a5b-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="34a5b-106">Syntax</span></span>  
  
```xml  
<add name = "typeName" type="fully qualified type [,Version=version number] [,Culture=culture] [,PublicKeyToken= token]"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="34a5b-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="34a5b-107">Attributes and Elements</span></span>  

 <span data-ttu-id="34a5b-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="34a5b-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="34a5b-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="34a5b-109">Attributes</span></span>  
  
|<span data-ttu-id="34a5b-110">Attribut</span><span class="sxs-lookup"><span data-stu-id="34a5b-110">Attribute</span></span>|<span data-ttu-id="34a5b-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="34a5b-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="34a5b-112">**name**</span><span class="sxs-lookup"><span data-stu-id="34a5b-112">**name**</span></span>|<span data-ttu-id="34a5b-113">Ein einfacher Name, der zum Suchen der Instanz verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="34a5b-113">A simple name that is used to find the instance.</span></span>|  
|<span data-ttu-id="34a5b-114">**Typ**</span><span class="sxs-lookup"><span data-stu-id="34a5b-114">**type**</span></span>|<span data-ttu-id="34a5b-115">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="34a5b-115">Required.</span></span> <span data-ttu-id="34a5b-116">Gibt die Schemaerweiterungsklasse an, die hinzugefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="34a5b-116">Specifies the schema  extension class to add.</span></span> <span data-ttu-id="34a5b-117">Der Wert des **type**-Attributs muss sich in einer Zeile befinden und schließt den vollständigen Typnamen enthalten.</span><span class="sxs-lookup"><span data-stu-id="34a5b-117">The **type** attribute value must be on one line, and include the fully qualified type name.</span></span> <span data-ttu-id="34a5b-118">Wenn die Assembly im globalen Assemblycache (GAC) gespeichert ist, muss außerdem die Version, die Kultur und das Token des öffentlichen Schlüssels der signierten Assembly enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="34a5b-118">When the assembly is placed in the Global Assembly Cache (GAC), it must also include the version, culture, and public key token of the signed assembly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="34a5b-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="34a5b-119">Child Elements</span></span>  

 <span data-ttu-id="34a5b-120">Keine</span><span class="sxs-lookup"><span data-stu-id="34a5b-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="34a5b-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="34a5b-121">Parent Elements</span></span>  
  
|<span data-ttu-id="34a5b-122">Element</span><span class="sxs-lookup"><span data-stu-id="34a5b-122">Element</span></span>|<span data-ttu-id="34a5b-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="34a5b-123">Description</span></span>|  
|-------------|-----------------|  
|\<schemaImporterExtensions>|<span data-ttu-id="34a5b-124">Enthält die Typen, die von der <xref:System.Xml.Serialization.XmlSchemaImporter>-Klasse verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="34a5b-124">Contains the types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter>.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="34a5b-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="34a5b-125">Example</span></span>  

 <span data-ttu-id="34a5b-126">Im folgenden Codebeispiel wird ein Erweiterungstyp hinzugefügt, den XmlSchemaImporter zum Zuordnen von Typen verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="34a5b-126">The following code example adds an extension type that the XmlSchemaImporter can use when mapping types.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="34a5b-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="34a5b-127">See also</span></span>

- <xref:System.Xml.Serialization.XmlSchemaImporter>
- [<span data-ttu-id="34a5b-128">\<system.xml.serialization>-Element</span><span class="sxs-lookup"><span data-stu-id="34a5b-128">\<system.xml.serialization> Element</span></span>](system-xml-serialization-element.md)
- [<span data-ttu-id="34a5b-129">\<schemaImporterExtensions>-Element</span><span class="sxs-lookup"><span data-stu-id="34a5b-129">\<schemaImporterExtensions> Element</span></span>](schemaimporterextensions-element.md)

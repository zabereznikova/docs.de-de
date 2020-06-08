---
title: <system.xml.serialization>-Element
description: In diesem Artikel wird das <system.xml.serialization>-Element beschrieben, das Element der obersten Ebene zum Steuern der XML-Serialisierung.
ms.date: 03/30/2017
helpviewer_keywords:
- system.xml.serialization element
- XML serialization, configuration
- <system.xml.serialization> element
ms.assetid: 3ce45919-388a-418c-8968-6df0372c73ec
ms.openlocfilehash: f69e80592e9321de64421b977a63b83d8be2ad9e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "84289485"
---
# <a name="systemxmlserialization-element"></a>\<system.xml.serialization>-Element

Das Element der obersten Ebene zur Steuerung der XML-Serialisierung. Weitere Informationen zu Konfigurationsdateien finden Sie unter [Konfigurationsdateienschema](../../framework/configure-apps/file-schema/index.md).

\<configuration>\
\<system.xml.serialization>

## <a name="syntax"></a>Syntax

```xml
<system.xml.serialization>
</system.xml.serialization>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[\<dateTimeSerialization>-Element](datetimeserialization-element.md)|Bestimmt den Serialisierungsmodus von <xref:System.DateTime>-Objekten.|
|[\<schemaImporterExtensions>-Element](schemaimporterextensions-element.md)|Enthält Typen, die von der <xref:System.Xml.Serialization.XmlSchemaImporter>-Klasse zum Zuordnen von XSD-Typen zu .NET Framework-Typen verwendet werden.|

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[\<configuration>-Element](../../framework/configure-apps/file-schema/configuration-element.md)|Das Stammelement in jeder Konfigurationsdatei, die von der Common Language Runtime und den .NET Framework-Anwendungen verwendet wird.|

## <a name="example"></a>Beispiel

Das folgende Codebeispiel veranschaulicht, wie der Serialisierungsmodus eines <xref:System.DateTime>-Objekts und das Hinzufügen von Typen, die von <xref:System.Xml.Serialization.XmlSchemaImporter> verwendet werden, beim Zuordnen von XSD-Typen zu .NET Framework-Typen festgelegt werden.

```xml
<system.xml.serialization>
    <xmlSerializer checkDeserializeAdvances="false" />
    <dateTimeSerialization mode = "Local" />
    <schemaImporterExtensions>
        <add
        name = "MobileCapabilities"
        type = "System.Web.Mobile.MobileCapabilities,
        System.Web.Mobile, Version=2.0.0.0, Culture=neutral,
        PublicKeyToken=b03f5f6f11d40a3a" />
    </schemaImporterExtensions>
</system.xml.serialization>
```

## <a name="see-also"></a>Siehe auch

- <xref:System.Xml.Serialization.XmlSchemaImporter>
- <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>
- [Konfigurationsdateischema](../../framework/configure-apps/file-schema/index.md)
- [\<dateTimeSerialization>-Element](datetimeserialization-element.md)
- [\<schemaImporterExtensions>-Element](schemaimporterextensions-element.md)
- [\<add>-Element für \<schemaImporterExtensions>](add-element-for-schemaimporterextensions.md)

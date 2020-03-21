---
title: XmlReader.CreateSqlReader-Methode (System.Xml)
ms.date: 10/17/2019
topic_type:
- apiref
api_name:
- System.Xml.XmlReader.CreateSqlReader
api_location:
- system.xml.dll
api_type:
- Assembly
ms.openlocfilehash: 7bd2ef5158516acede47f73f9937d06159bc16c9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155738"
---
# <a name="xmlreadercreatesqlreader-method"></a>XmlReader.CreateSqlReader-Methode

Erstellt mit dem angegebenen Stream, den Einstellungen und den Kontextinformationen für Analysezwecke eine neue <xref:System.Xml.XmlReader>-Instanz.

```csharp
internal static XmlReader CreateSqlReader(Stream input,
  XmlReaderSettings settings, XmlParserContext inputContext)
```

## <a name="parameters"></a>Parameter

- `input` <xref:System.IO.Stream>  
  Der Stream, der die XML-Daten enthält.

- `settings` <xref:System.Xml.XmlReaderSettings>  
  Die Einstellungen für die neue <xref:System.Xml.XmlReader>-Instanz. Dieser Wert kann `null` sein.

- `inputContext` <xref:System.Xml.XmlParserContext>  
  Die Kontextinformationen, die zum Analysieren des XML-Fragments erforderlich sind. Dieser Wert kann `null` sein.

## <a name="returns"></a>Rückgabe

<xref:System.Xml.XmlReader>  
Ein Objekt, mit dem die im Stream enthaltenen XML-Daten gelesen werden.

## <a name="remarks"></a>Bemerkungen

> [!WARNING]
> Die `XmlReader.CreateSqlReader` Methode ist intern und soll nicht direkt in Ihrem Code verwendet werden.
>
> Microsoft unterstützt die Verwendung dieser Methode in einer Produktionsanwendung unter keinen Umständen.

## <a name="requirements"></a>Requirements (Anforderungen)

**Namespace:**<xref:System.Xml>

**Montage:** System.Xml.dll

**.NET Framework-Versionen:** Verfügbar seit 2.0.

---
title: XmlReader. kreatesqlreader-Methode (System. Xml)
ms.date: 10/17/2019
topic_type:
- apiref
api_name:
- System.Xml.XmlReader.CreateSqlReader
api_location:
- system.xml.dll
api_type:
- Assembly
ms.openlocfilehash: c65ef7c073175488c11c5e912a44d46fd4319209
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "77215449"
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
> Die `XmlReader.CreateSqlReader`-Methode ist intern und sollte nicht direkt im Code verwendet werden.
>
> Microsoft unterstützt die Verwendung dieser Methode in einer Produktionsanwendung unter keinen Umständen.

## <a name="requirements"></a>Requirements (Anforderungen)

**Namespace:** <xref:System.Xml>

**Assembly:** System. Xml. dll

**.NET Framework Versionen:** Verfügbar seit 2,0.

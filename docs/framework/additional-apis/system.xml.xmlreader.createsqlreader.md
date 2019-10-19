---
title: XmlReader. kreatesqlreader-Methode (System. Xml)
author: mairaw
ms.author: mairaw
ms.date: 10/17/2019
topic_type:
- apiref
api_name:
- System.Xml.XmlReader.CreateSqlReader
api_location:
- system.xml.dll
api_type:
- Assembly
ms.openlocfilehash: 302be4eff32d2c96a1571d291e0b289e77694db8
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582781"
---
# <a name="xmlreadercreatesqlreader-method"></a>XmlReader. kreatesqlreader-Methode

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

## <a name="remarks"></a>Hinweise

> [!WARNING]
> Die `XmlReader.CreateSqlReader`-Methode ist intern und sollte nicht direkt im Code verwendet werden.
>
> Microsoft unterstützt die Verwendung dieser Methode in einer Produktionsanwendung unter keinen Umständen.

## <a name="requirements"></a>Anforderungen

**Namespace:** <xref:System.Xml>

**Assembly:** System. Xml. dll

**.NET Framework Versionen:** Verfügbar seit 2,0.

---
title: XmlDictionaryReaderQuotas
ms.date: 03/30/2017
ms.assetid: 9b4ca8b4-0a89-4758-97ab-528a8ce18f07
ms.openlocfilehash: f1c12a0a60397a84d4e9ff0241c4182b4511af5c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59767707"
---
# <a name="xmldictionaryreaderquotas"></a>XmlDictionaryReaderQuotas
XmlDictionaryReaderQuotas  
  
## <a name="syntax"></a>Syntax  
  
```csharp
class XmlDictionaryReaderQuotas  
{  
  sint32 MaxArrayLength;  
  sint32 MaxBytesPerRead;  
  sint32 MaxDepth;  
  sint32 MaxNameTableCharCount;  
  sint32 MaxStringContentLength;  
};  
```  
  
## <a name="methods"></a>Methoden  
 Von der XmlDictionaryReaderQuotas-Klasse werden keine Methoden definiert.  
  
## <a name="properties"></a>Eigenschaften  
 Die XmlDictionaryReaderQuotas-Klasse weist die folgenden Eigenschaften auf:  
  
### <a name="maxarraylength"></a>MaxArrayLength  
 Datentyp: sint32  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die maximal zulässige Arraylänge.  
  
### <a name="maxbytesperread"></a>MaxBytesPerRead  
 Datentyp: sint32  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die maximal zulässigen Bytes, die bei jedem Lesevorgang zurückgegeben werden.  
  
### <a name="maxdepth"></a>MaxDepth  
 Datentyp: sint32  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die maximale geschachtelte Knotentiefe für jeden Lesevorgang.  
  
### <a name="maxnametablecharcount"></a>MaxNameTableCharCount  
 Datentyp: sint32  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die maximal zulässigen Zeichen in einem Tabellennamen.  
  
### <a name="maxstringcontentlength"></a>MaxStringContentLength  
 Datentyp: sint32  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die maximale Zeichenanzahl, die in XML-Elementinhalten zulässig ist.  
  
## <a name="requirements"></a>Anforderungen  
  
|MOF|Deklariert in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Namespace|Definiert in root\ServiceModel|  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Xml.XmlDictionaryReaderQuotas>
- <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>

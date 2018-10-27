---
title: XmlDictionaryReaderQuotas
ms.date: 03/30/2017
ms.assetid: 9b4ca8b4-0a89-4758-97ab-528a8ce18f07
ms.openlocfilehash: 9bc519509b00383be333ac605688950d2709117c
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50044228"
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
 <xref:System.Xml.XmlDictionaryReaderQuotas>  
 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>

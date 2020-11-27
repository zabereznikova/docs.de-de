---
title: XmlDictionaryReaderQuotas
ms.date: 03/30/2017
ms.assetid: 9b4ca8b4-0a89-4758-97ab-528a8ce18f07
ms.openlocfilehash: c5bb7813a680c89eb90f4ccf4ed6f09a831c8095
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96262202"
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
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Xml.XmlDictionaryReaderQuotas>
- <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>

---
title: MtomMessageEncodingBindingElement
ms.date: 03/30/2017
ms.assetid: 4a9c6c3d-e561-4b2d-a693-7e84bdd3534a
ms.openlocfilehash: b4d8503543c93d0112fc39e4b2dba5434bc56472
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96237403"
---
# <a name="mtommessageencodingbindingelement"></a>MtomMessageEncodingBindingElement

MtomMessageEncodingBindingElement  
  
## <a name="syntax"></a>Syntax  
  
```csharp
class MtomMessageEncodingBindingElement : MessageEncodingBindingElement  
{  
  string Encoding;  
  sint32 MaxReadPoolSize;  
  sint32 MaxWritePoolSize;  
  XmlDictionaryReaderQuotas ReaderQuotas;  
};  
```  
  
## <a name="methods"></a>Methoden  

 Die Klasse MtomMessageEncodingBindingElement definiert keine Methoden.  
  
## <a name="properties"></a>Eigenschaften  

 Die Klasse MtomMessageEncodingBindingElement verfügt über die folgenden Eigenschaften:  
  
### <a name="encoding"></a>Codierung  

 Datentyp: String  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die Zeichensatzcodierung, die zum Ausgeben von Nachrichten über die Bindung verwendet werden soll.  
  
### <a name="maxreadpoolsize"></a>MaxReadPoolSize  

 Datentyp: sint32  
  
 Zugriffstyp: Schreibgeschützt  
  
 Eine ganze Zahl, die definiert, wie viele Nachrichten gleichzeitig gelesen werden können, ohne neue Leser zuzuordnen.  
  
### <a name="maxwritepoolsize"></a>MaxWritePoolSize  

 Datentyp: sint32  
  
 Zugriffstyp: Schreibgeschützt  
  
 Eine ganze Zahl, die definiert, wie viele Nachrichten gleichzeitig gesendet werden können, ohne neue Schreiber zuzuordnen.  
  
### <a name="readerquotas"></a>ReaderQuotas  

 Datentyp: XmlDictionaryReaderQuotas  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die Kontingente der Leser.  
  
## <a name="requirements"></a>Anforderungen  
  
|MOF|Deklariert in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Namespace|Definiert in root\ServiceModel|  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>

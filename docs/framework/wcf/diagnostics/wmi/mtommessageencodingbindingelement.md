---
title: MtomMessageEncodingBindingElement
ms.date: 03/30/2017
ms.assetid: 4a9c6c3d-e561-4b2d-a693-7e84bdd3534a
ms.openlocfilehash: aed65311d2b36a5dc764511de04e34c4bfb69d7b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2019
ms.locfileid: "59978171"
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
 Datentyp: string (Zeichenfolge)  
  
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
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>

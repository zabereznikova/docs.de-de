---
title: "Versionstolerante Serialisierungsrückrufe"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- OnDeserializedAttribute [WCF]
- OnDeserializingAttribute [WCF]
- OnSerializingAttribute [WCF]
- serialization [WCF], setting default values
- OnSerializedAttribute [WCF]
ms.assetid: aa4a3a6f-05ec-4efd-bdbf-2181e13e6468
caps.latest.revision: "17"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7c00cadd4b0e643e35f7f56a28760e261c423699
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="version-tolerant-serialization-callbacks"></a>Versionstolerante Serialisierungsrückrufe
Die von den Klassen <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> und <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> unterstützten Methoden für versionstolerante Serialisierungsrückrufe werden vom Datenvertrags-Programmiermodell vollständig unterstützt.  
  
## <a name="version-tolerant-attributes"></a>Versionstolerante Attribute  
 Es gibt vier Rückrufattribute. Jedes Attribut kann für eine Methode angewendet werden, die das Serialisierungs-/Deserialisierungmodul zu verschiedenen Zeiten aufruft. In der folgenden Tabelle wird erläutert, wann die einzelnen Attribute verwendet werden.  
  
|Attribut|Beim Aufruf der entsprechenden Methode|  
|---------------|---------------------------------------------|  
|<xref:System.Runtime.Serialization.OnSerializingAttribute>|Der Aufruf erfolgt vor dem Serialisieren des Typs.|  
|<xref:System.Runtime.Serialization.OnSerializedAttribute>|Der Aufruf erfolgt nach dem Serialisieren des Typs.|  
|<xref:System.Runtime.Serialization.OnDeserializingAttribute>|Der Aufruf erfolgt vor dem Deserialisieren des Typs.|  
|<xref:System.Runtime.Serialization.OnDeserializedAttribute>|Der Aufruf erfolgt nach dem Deserialisieren des Typs.|  
  
 Diese Methode muss einen <xref:System.Runtime.Serialization.StreamingContext>-Parameter akzeptieren.  
  
 Diese Methoden sind in erster Linie für die Verwendung mit der Versionsverwaltung oder der Initialisierung bestimmt. Während der Deserialisierung werden keine Konstruktoren aufgerufen. Datenmember werden deshalb möglicherweise nicht ordnungsgemäß initialisiert (auf beabsichtigte Standardwerte), falls die Daten für diese Member im eingehenden Stream fehlen. Das kann z.&#160;B. der Fall sein, wenn die Daten aus einer früheren Version eines Typs stammen, bei dem einige Datenmember fehlen. Verwenden Sie die mit <xref:System.Runtime.Serialization.OnDeserializingAttribute> gekennzeichnete Methode, wie im folgenden Beispiel dargestellt, um dieses Problem zu beheben.  
  
 Mit jedem der oben aufgeführten Rückrufattribute kann nur eine Methode pro Typ gekennzeichnet werden.  
  
### <a name="example"></a>Beispiel  
 [!code-csharp[C_DataContract#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontract/cs/source.cs#9)]
 [!code-vb[C_DataContract#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontract/vb/source.vb#9)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Runtime.Serialization.OnSerializingAttribute>  
 <xref:System.Runtime.Serialization.OnSerializedAttribute>  
 <xref:System.Runtime.Serialization.OnDeserializingAttribute>  
 <xref:System.Runtime.Serialization.OnDeserializedAttribute>  
 <xref:System.Runtime.Serialization.StreamingContext>  
 [Versionstolerante Serialisierung](../../../../docs/standard/serialization/version-tolerant-serialization.md)

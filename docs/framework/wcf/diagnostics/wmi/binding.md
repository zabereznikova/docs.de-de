---
title: Binding2
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 09511c6c-5749-4bb0-874e-0f0be36bfe04
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 6505fa08ca43e64df224b75500aacbc903783398
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="binding"></a>Bindung
wmi-Bindung  
  
## <a name="syntax"></a>Syntax  
  
```  
class Binding  
{  
  BindingElement BindingElements[];  
  datetime CloseTimeout;  
  string Name;  
  string Namespace;  
  datetime OpenTimeout;  
  datetime ReceiveTimeout;  
  string Scheme;  
  datetime SendTimeout;  
};  
```  
  
## <a name="methods"></a>Methoden  
 Die Bindungsklasse definiert keine Methoden.  
  
## <a name="properties"></a>Eigenschaften  
 Die Bindungsklasse verfügt über die folgenden Eigenschaften.  
  
### <a name="bindingelements"></a>BindingElements  
 Datentyp: BindingElement-Array  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die Auflistung der durch die Bindung implementierten Bindungselemente.  
  
### <a name="closetimeout"></a>CloseTimeout  
 Datentyp: Zeitpunkt (Datum und Uhrzeit)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Das Zeitintervall, das für den Abschluss eines Schließvorgangs bereitgestellt wird.  
  
### <a name="name"></a>Name  
 Datentyp: string (Zeichenfolge)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Der Name der Bindung.  
  
### <a name="namespace"></a>Namespace  
 Datentyp: string (Zeichenfolge)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Der XML-Namespace der Bindung.  
  
### <a name="opentimeout"></a>OpenTimeout  
 Datentyp: Zeitpunkt (Datum und Uhrzeit)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Das Zeitintervall, das für den Abschluss eines Öffnungsvorgangs bereitgestellt wird.  
  
### <a name="receivetimeout"></a>ReceiveTimeout  
 Datentyp: Zeitpunkt (Datum und Uhrzeit)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Das Zeitintervall, das für den Abschluss eines Empfangsvorgangs bereitgestellt wird.  
  
### <a name="scheme"></a>Schema  
 Datentyp: string (Zeichenfolge)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Das URI-Transportschema, das von den Kanal- und Listener-Factorys verwendet wird, die von der Bindung erstellt werden.  
  
### <a name="sendtimeout"></a>SendTimeout  
 Datentyp: Zeitpunkt (Datum und Uhrzeit)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Das Zeitintervall, das für den Abschluss eines Sendevorgangs bereitgestellt wird.  
  
## <a name="requirements"></a>Anforderungen  
  
|MOF|Deklariert in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Namespace|Definiert in root\ServiceModel|  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Channels.Binding>

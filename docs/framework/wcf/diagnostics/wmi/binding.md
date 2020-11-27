---
title: Binding2
ms.date: 03/30/2017
ms.assetid: 09511c6c-5749-4bb0-874e-0f0be36bfe04
ms.openlocfilehash: b72bd3903b7139c4adf2a8bd0ced6c34e7285640
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96274295"
---
# <a name="binding"></a>Bindung

wmi-Bindung  
  
## <a name="syntax"></a>Syntax  
  
```csharp
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

 Datentyp: String  
  
 Zugriffstyp: Schreibgeschützt  
  
 Der Name der Bindung.  
  
### <a name="namespace"></a>Namespace  

 Datentyp: String  
  
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

 Datentyp: String  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.Channels.Binding>

---
title: ServiceDebugBehavior
ms.date: 03/30/2017
ms.assetid: a5ec9061-1e95-43fb-b0d9-dbd0a7bc3c44
ms.openlocfilehash: dba4abd74cdddeb2b641feec5902413fe0704b1f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96262293"
---
# <a name="servicedebugbehavior"></a>ServiceDebugBehavior

ServiceDebugBehavior  
  
## <a name="syntax"></a>Syntax  
  
```csharp
class ServiceDebugBehavior : Behavior  
{  
  boolean HttpHelpPageEnabled;  
  string HttpHelpPageUrl;  
  boolean HttpsHelpPageEnabled;  
  string HttpsHelpPageUrl;  
  boolean IncludeExceptionDetailInFaults;  
};  
```  
  
## <a name="methods"></a>Methoden  

 Die ServiceDebugBehavior-Klasse definiert keine Methoden.  
  
## <a name="properties"></a>Eigenschaften  

 Die ServiceDebugBehavior-Klasse verfügt über die folgenden Eigenschaften:  
  
### <a name="httphelppageenabled"></a>HttpHelpPageEnabled  

 Datentyp: Boolesch  
  
 Zugriffstyp: Schreibgeschützt  
  
 Steuert, ob der Dienst seine WSDL unter der vom `HttpGetUrl`-Attribut gesteuerten Adresse veröffentlicht.  
  
### <a name="httphelppageurl"></a>HttpHelpPageUrl  

 Datentyp: String  
  
 Zugriffstyp: Schreibgeschützt  
  
 Legt den Speicherort fest, an dem die Dienst-WSDL für den Abruf mithilfe von HTTPS veröffentlicht wird.  
  
### <a name="httpshelppageenabled"></a>HttpsHelpPageEnabled  

 Datentyp: Boolesch  
  
 Zugriffstyp: Schreibgeschützt  
  
 Steuert, ob der Dienst seine WSDL oder HTTPS unter der vom `HttpsGetUrl`-Attribut gesteuerten Adresse veröffentlicht.  
  
### <a name="httpshelppageurl"></a>HttpsHelpPageUrl  

 Datentyp: String  
  
 Zugriffstyp: Schreibgeschützt  
  
 Legt den Speicherort fest, an dem die Dienst-WSDL für den Abruf mithilfe von HTTPS veröffentlicht wird.  
  
### <a name="includeexceptiondetailinfaults"></a>IncludeExceptionDetailInFaults  

 Datentyp: Boolesch  
  
 Zugriffstyp: Schreibgeschützt  
  
 Gibt an, ob verwaltete Ausnahmeinformationen in Details der SOAP-Fehler für Debugzwecke an die Clients zurückgegeben werden.  
  
## <a name="requirements"></a>Anforderungen  
  
|MOF|Deklariert in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Namespace|Definiert in root\ServiceModel|  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.Description.ServiceDebugBehavior>

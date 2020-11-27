---
title: ServiceSecurityAuditBehavior
ms.date: 03/30/2017
ms.assetid: 2c5809e7-5364-44ce-bc71-848be4672e2a
ms.openlocfilehash: 9da8f77ee8ea5dc8b22ac5c0cb5113e906c5dc78
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96262267"
---
# <a name="servicesecurityauditbehavior"></a>ServiceSecurityAuditBehavior

ServiceSecurityAuditBehavior  
  
## <a name="syntax"></a>Syntax  
  
```csharp  
class ServiceSecurityAuditBehavior : Behavior  
{  
  string AuditLogLocation;  
  string MessageAuthenticationAuditLevel;  
  string ServiceAuthorizationAuditLevel;  
  boolean SuppressAuditFailure;  
};  
```  
  
## <a name="methods"></a>Methoden  

 Die ServiceSecurityAuditBehavior-Klasse definiert keine Methoden.  
  
## <a name="properties"></a>Eigenschaften  

 Die ServiceSecurityAuditBehavior-Klasse verfügt über die folgenden Eigenschaften:  
  
### <a name="auditloglocation"></a>AuditLogLocation  

 Datentyp: String  
  
 Zugriffstyp: Schreibgeschützt  
  
 Der Speicherort des Überwachungsprotokolls.  
  
### <a name="messageauthenticationauditlevel"></a>MessageAuthenticationAuditLevel  

 Datentyp: String  
  
 Zugriffstyp: Schreibgeschützt  
  
 Typ der Meldungsauthentifizierungsebene, die verwendet wird, um Überwachungsereignisse zu protokollieren.  
  
### <a name="serviceauthorizationauditlevel"></a>ServiceAuthorizationAuditLevel  

 Datentyp: String  
  
 Zugriffstyp: Schreibgeschützt  
  
 Typen von Autorisierungsereignissen, die im Überwachungsprotokoll aufgezeichnet werden.  
  
### <a name="suppressauditfailure"></a>SuppressAuditFailure  

 Datentyp: Boolesch  
  
 Zugriffstyp: Schreibgeschützt  
  
 Boolescher Wert, der das Verhalten für das Unterdrücken von Fehlern beim Schreiben in das Überwachungsprotokoll angibt.  
  
## <a name="requirements"></a>Anforderungen  
  
|MOF|Deklariert in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Namespace|Definiert in root\ServiceModel|  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>

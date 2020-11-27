---
title: ServiceAuthorizationBehavior
ms.date: 03/30/2017
ms.assetid: 77dad8e8-fea4-4d1c-b366-2f01a2a87f78
ms.openlocfilehash: d3625865484568746888ef0638d9a8501e610bef
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96273203"
---
# <a name="serviceauthorizationbehavior"></a>ServiceAuthorizationBehavior

ServiceAuthorizationBehavior  
  
## <a name="syntax"></a>Syntax  
  
```csharp
class ServiceAuthorizationBehavior : Behavior  
{  
  boolean ImpersonateCallerForAllOperations;  
  string PrincipalPermissionMode;  
  string RoleProvider;  
  string ServiceAuthorizationManager;  
};  
```  
  
## <a name="methods"></a>Methoden  

 Die ServiceAuthorizationBehavior-Klasse definiert keine Methoden.  
  
## <a name="properties"></a>Eigenschaften  

 Die ServiceAuthorizationBehavior-Klasse verfügt über folgende Eigenschaften:  
  
### <a name="impersonatecallerforalloperations"></a>ImpersonateCallerForAllOperations  

 Datentyp: Boolesch  
  
 Zugriffstyp: Schreibgeschützt  
  
 Ein Wert, der kontrolliert, ob der Dienst versucht, mithilfe der Anmeldeinformationen der eingehenden Nachricht einen Identitätswechsel durchzuführen.  
  
### <a name="principalpermissionmode"></a>PrincipalPermissionMode  

 Datentyp: String  
  
 Zugriffstyp: Schreibgeschützt  
  
 Ruft den Prinzipal ab, mit dem Vorgänge auf dem Server ausgeführt werden.  
  
### <a name="roleprovider"></a>RoleProvider  

 Datentyp: String  
  
 Zugriffstyp: Schreibgeschützt  
  
 Der Name des ASP.NET-Rollenanbieters.  
  
### <a name="serviceauthorizationmanager"></a>ServiceAuthorizationManager  

 Datentyp: String  
  
 Zugriffstyp: Schreibgeschützt  
  
 Der Autorisierungs-Manager für die benutzerdefinierte Autorisierung.  
  
## <a name="requirements"></a>Anforderungen  
  
|MOF|Deklariert in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Namespace|Definiert in root\ServiceModel|  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>

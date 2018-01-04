---
title: ServiceAuthorizationBehavior
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 77dad8e8-fea4-4d1c-b366-2f01a2a87f78
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 62f3e32e886f49ac8dde6af5c37a4e57373c9576
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="serviceauthorizationbehavior"></a>ServiceAuthorizationBehavior
ServiceAuthorizationBehavior  
  
## <a name="syntax"></a>Syntax  
  
```  
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
 Datentyp: string (Zeichenfolge)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Ruft den Prinzipal ab, mit dem Vorgänge auf dem Server ausgeführt werden.  
  
### <a name="roleprovider"></a>RoleProvider  
 Datentyp: string (Zeichenfolge)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Der Name des ASP.NET-Rollenanbieters.  
  
### <a name="serviceauthorizationmanager"></a>ServiceAuthorizationManager  
 Datentyp: string (Zeichenfolge)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Der Autorisierungs-Manager für die benutzerdefinierte Autorisierung.  
  
## <a name="requirements"></a>Anforderungen  
  
|MOF|Deklariert in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Namespace|Definiert in root\ServiceModel|  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>

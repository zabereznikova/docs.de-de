---
title: ServiceCredentials
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9c780793-4785-46f7-add9-ac1ebeadb614
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 73fad36b5bf14745ca70d297fa988b90d46990df
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="servicecredentials"></a>ServiceCredentials
ServiceCredentials  
  
## <a name="syntax"></a>Syntax  
  
```  
class ServiceCredentials : Behavior  
{  
  string ClientCertificate;  
  string IssuedTokenAuthentication;  
  string Peer;  
  string SecureConversationAuthentication;  
  string ServiceCertificate;  
  string UserNameAuthentication;  
  string WindowsAuthentication;  
};  
```  
  
## <a name="methods"></a>Methoden  
 Die Klasse ServiceCredentials definiert keine Methoden.  
  
## <a name="properties"></a>Eigenschaften  
 Die Klasse ServiceCredentials verfügt über die folgenden Eigenschaften:  
  
### <a name="clientcertificate"></a>ClientCertificate  
 Datentyp: string (Zeichenfolge)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die Authentifizierungs- und Bereitstellungseinstellungen des Clientzertifikats für diesen Dienst.  
  
### <a name="issuedtokenauthentication"></a>IssuedTokenAuthentication  
 Datentyp: string (Zeichenfolge)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die Authentifizierungseinstellungen des aktuell ausgegebenen Tokens für diesen Dienst.  
  
### <a name="peer"></a>Peer  
 Datentyp: string (Zeichenfolge)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die aktuellen Authentifizierungs- und Bereitstellungseinstellungen für Anmeldeinformationen, die von Peertransportendpunkten verwendet werden sollen.  
  
### <a name="secureconversationauthentication"></a>SecureConversationAuthentication  
 Datentyp: string (Zeichenfolge)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Gibt die aktuellen sicheren Konversationseinstellungen an.  
  
### <a name="servicecertificate"></a>ServiceCertificate  
 Datentyp: string (Zeichenfolge)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Das diesem Dienst zugeordnete Zertifikat.  
  
### <a name="usernameauthentication"></a>UserNameAuthentication  
 Datentyp: string (Zeichenfolge)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die Benutzernamen-/Kennworteinstellungen für diesen Dienst.  
  
### <a name="windowsauthentication"></a>WindowsAuthentication  
 Datentyp: string (Zeichenfolge)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die Windows-Authentifizierungseinstellungen für diesen Dienst.  
  
## <a name="requirements"></a>Anforderungen  
  
|MOF|Deklariert in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Namespace|Definiert in root\ServiceModel|  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Description.ServiceCredentials>

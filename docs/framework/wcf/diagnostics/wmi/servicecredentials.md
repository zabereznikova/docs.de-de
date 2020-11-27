---
title: ServiceCredentials
ms.date: 03/30/2017
ms.assetid: 9c780793-4785-46f7-add9-ac1ebeadb614
ms.openlocfilehash: d7e89acedc8fc1004b0198172e58813944df85f3
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96262306"
---
# <a name="servicecredentials"></a>ServiceCredentials

ServiceCredentials  
  
## <a name="syntax"></a>Syntax  
  
```csharp
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

 Datentyp: String  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die Authentifizierungs- und Bereitstellungseinstellungen des Clientzertifikats für diesen Dienst.  
  
### <a name="issuedtokenauthentication"></a>IssuedTokenAuthentication  

 Datentyp: String  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die Authentifizierungseinstellungen des aktuell ausgegebenen Tokens für diesen Dienst.  
  
### <a name="peer"></a>Peer  

 Datentyp: String  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die aktuellen Authentifizierungs- und Bereitstellungseinstellungen für Anmeldeinformationen, die von Peertransportendpunkten verwendet werden sollen.  
  
### <a name="secureconversationauthentication"></a>SecureConversationAuthentication  

 Datentyp: String  
  
 Zugriffstyp: Schreibgeschützt  
  
 Gibt die aktuellen sicheren Konversationseinstellungen an.  
  
### <a name="servicecertificate"></a>ServiceCertificate  

 Datentyp: String  
  
 Zugriffstyp: Schreibgeschützt  
  
 Das diesem Dienst zugeordnete Zertifikat.  
  
### <a name="usernameauthentication"></a>UserNameAuthentication  

 Datentyp: String  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die Benutzernamen-/Kennworteinstellungen für diesen Dienst.  
  
### <a name="windowsauthentication"></a>WindowsAuthentication  

 Datentyp: String  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die Windows-Authentifizierungseinstellungen für diesen Dienst.  
  
## <a name="requirements"></a>Anforderungen  
  
|MOF|Deklariert in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Namespace|Definiert in root\ServiceModel|  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.Description.ServiceCredentials>

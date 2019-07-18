---
title: ServiceCredentials
ms.date: 03/30/2017
ms.assetid: 9c780793-4785-46f7-add9-ac1ebeadb614
ms.openlocfilehash: d9563bd3bfe067ad83bfa03e7c6375a9db933f14
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61956978"
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

- <xref:System.ServiceModel.Description.ServiceCredentials>

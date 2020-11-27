---
title: ClientCredentials
ms.date: 03/30/2017
ms.assetid: 41dffd6b-8f14-4fed-aefb-2a1bb168efb3
ms.openlocfilehash: c63e1b3de464b306f46e2f0935b1208d7262925a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96274191"
---
# <a name="clientcredentials"></a>ClientCredentials

ClientCredentials  
  
## <a name="syntax"></a>Syntax  
  
```csharp
class ClientCredentials : Behavior  
{  
  string ClientCertificate;  
  string HttpDigest;  
  string IssuedToken;  
  string Peer;  
  string ServiceCertificate;  
  boolean SupportInteractive;  
  string UserName;  
  string Windows;  
};  
```  
  
## <a name="methods"></a>Methoden  

 Die Klasse ClientCredentials definiert keine Methoden.  
  
## <a name="properties"></a>Eigenschaften  

 Die Klasse ClientCredentials verfügt über die folgenden Eigenschaften:  
  
### <a name="clientcertificate"></a>ClientCertificate  

 Datentyp: String  
  
 Zugriffstyp: Schreibgeschützt  
  
 Das X.509-Zertifikat, das der Client benutzt, um den Dienst zu authentifizieren.  
  
### <a name="httpdigest"></a>HttpDigest  

 Datentyp: String  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die aktuellen Http-Digestanmeldeinformationen.  
  
### <a name="issuedtoken"></a>IssuedToken  

 Datentyp: String  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die Endpunktadresse und die Bindung, die verwendet werden, um den lokalen Sicherheitstokendienst anzusprechen.  
  
### <a name="peer"></a>Peer  

 Datentyp: String  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die Anmeldeinformationen, die der Peerknoten verwendet, um sich anderen Knoten im Netz gegenüber zu authentifizieren.  
  
### <a name="servicecertificate"></a>ServiceCertificate  

 Datentyp: String  
  
 Zugriffstyp: Schreibgeschützt  
  
 Das X.509-Zertifikat des Diensts.  
  
### <a name="supportinteractive"></a>SupportInteractive  

 Datentyp: Boolesch  
  
 Zugriffstyp: Schreibgeschützt  
  
 Ein boolescher Wert, der festlegt, ob die Anmeldeinformationen interaktive Verhandlung unterstützen.  
  
### <a name="username"></a>UserName  

 Datentyp: String  
  
 Zugriffstyp: Schreibgeschützt  
  
 Der Benutzername und das Kennwort, die der Client verwendet, um sich dem Dienst gegenüber zu authentifizieren.  
  
### <a name="windows"></a>Windows  

 Datentyp: String  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die Windows-Anmeldeinformationen, die der Client verwendet, um sich dem Dienst gegenüber zu authentifizieren.  
  
## <a name="requirements"></a>Anforderungen  
  
|MOF|Deklariert in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Namespace|Definiert in root\ServiceModel|  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.Description.ClientCredentials>

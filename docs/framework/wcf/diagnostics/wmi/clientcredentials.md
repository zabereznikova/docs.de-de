---
title: ClientCredentials
ms.date: 03/30/2017
ms.assetid: 41dffd6b-8f14-4fed-aefb-2a1bb168efb3
ms.openlocfilehash: c3adc675bb6c1e9011459a88fd7dc8e8cf63a880
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61963973"
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
 Datentyp: string (Zeichenfolge)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Das X.509-Zertifikat, das der Client benutzt, um den Dienst zu authentifizieren.  
  
### <a name="httpdigest"></a>HttpDigest  
 Datentyp: string (Zeichenfolge)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die aktuellen Http-Digestanmeldeinformationen.  
  
### <a name="issuedtoken"></a>IssuedToken  
 Datentyp: string (Zeichenfolge)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die Endpunktadresse und die Bindung, die verwendet werden, um den lokalen Sicherheitstokendienst anzusprechen.  
  
### <a name="peer"></a>Peer  
 Datentyp: string (Zeichenfolge)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die Anmeldeinformationen, die der Peerknoten verwendet, um sich anderen Knoten im Netz gegenüber zu authentifizieren.  
  
### <a name="servicecertificate"></a>ServiceCertificate  
 Datentyp: string (Zeichenfolge)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Das X.509-Zertifikat des Diensts.  
  
### <a name="supportinteractive"></a>SupportInteractive  
 Datentyp: Boolesch  
  
 Zugriffstyp: Schreibgeschützt  
  
 Ein boolescher Wert, der festlegt, ob die Anmeldeinformationen interaktive Verhandlung unterstützen.  
  
### <a name="username"></a>UserName  
 Datentyp: string (Zeichenfolge)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Der Benutzername und das Kennwort, die der Client verwendet, um sich dem Dienst gegenüber zu authentifizieren.  
  
### <a name="windows"></a>Windows  
 Datentyp: string (Zeichenfolge)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die Windows-Anmeldeinformationen, die der Client verwendet, um sich dem Dienst gegenüber zu authentifizieren.  
  
## <a name="requirements"></a>Anforderungen  
  
|MOF|Deklariert in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Namespace|Definiert in root\ServiceModel|  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.Description.ClientCredentials>

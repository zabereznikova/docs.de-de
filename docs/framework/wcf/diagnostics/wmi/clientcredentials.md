---
title: "ClientCredentials | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 41dffd6b-8f14-4fed-aefb-2a1bb168efb3
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# ClientCredentials
ClientCredentials  
  
## Syntax  
  
```  
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
  
## Methoden  
 Die Klasse ClientCredentials definiert keine Methoden.  
  
## Eigenschaften  
 Die Klasse ClientCredentials verfügt über die folgenden Eigenschaften:  
  
### ClientCertificate  
 Datentyp: Zeichenfolge  
  
 Zugriffstyp: Schreibgeschützt  
  
 Das X.509\-Zertifikat, das der Client benutzt, um den Dienst zu authentifizieren.  
  
### HttpDigest  
 Datentyp: string \(Zeichenfolge\)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die aktuellen Http\-Digestanmeldeinformationen.  
  
### IssuedToken  
 Datentyp: string \(Zeichenfolge\)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die Endpunktadresse und die Bindung, die verwendet werden, um den lokalen Sicherheitstokendienst anzusprechen.  
  
### Peer  
 Datentyp: string \(Zeichenfolge\)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die Anmeldeinformationen, die der Peerknoten verwendet, um sich anderen Knoten im Netz gegenüber zu authentifizieren.  
  
### ServiceCertificate  
 Datentyp: string \(Zeichenfolge\)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Das X.509\-Zertifikat des Diensts.  
  
### SupportInteractive  
 Datentyp: Boolescher Wert  
  
 Zugriffstyp: Schreibgeschützt  
  
 Ein boolescher Wert, der festlegt, ob die Anmeldeinformationen interaktive Verhandlung unterstützen.  
  
### UserName  
 Datentyp: string \(Zeichenfolge\)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Der Benutzername und das Kennwort, die der Client verwendet, um sich dem Dienst gegenüber zu authentifizieren.  
  
### Windows  
 Datentyp: string \(Zeichenfolge\)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die Windows\-Anmeldeinformationen, die der Client verwendet, um sich dem Dienst gegenüber zu authentifizieren.  
  
## Voraussetzungen  
  
|MOF|Deklariert in Servicemodel.mof.|  
|---------|-------------------------------------|  
|Namespace|Definiert in root\\ServiceModel|  
  
## Siehe auch  
 <xref:System.ServiceModel.Description.ClientCredentials>
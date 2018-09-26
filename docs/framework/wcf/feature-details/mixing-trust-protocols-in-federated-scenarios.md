---
title: Verwenden mehrerer verschiedener Vertrauensprotokolle in Verbundszenarien
ms.date: 03/30/2017
ms.assetid: d7b5fee9-2246-4b09-b8d7-9e63cb817279
author: BrucePerlerMS
ms.openlocfilehash: d4290880d8d708811a95b38356aa61f0d23c89a8
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2018
ms.locfileid: "47090369"
---
# <a name="mixing-trust-protocols-in-federated-scenarios"></a>Verwenden mehrerer verschiedener Vertrauensprotokolle in Verbundszenarien
Unter bestimmten Bedingungen sind Szenarios denkbar, in denen Verbundclients mit einem Dienst und mit einem Security Token Service (STS) kommunizieren, die nicht die gleiche Trust-Version besitzen. Die Dienst-WSDL kann eine `RequestSecurityTokenTemplate`-Assertion mit WS-Trust-Elementen enthalten, die aus anderen Versionen stammen als der STS. In solchen Fällen konvertiert ein Windows Communication Foundation (WCF)-Client die WS-Trust-Elemente aus der `RequestSecurityTokenTemplate` entsprechend der STS-trust-Version. WCF behandelt nicht übereinstimmende Trust-Versionen nur für standardbindungen. Alle standardalgorithmusparameter, die von WCF erkannt werden, sind Teil der standardbindung. In diesem Thema wird beschrieben, die WCF-Verhalten mit verschiedenen vertrauenseinstellungen zwischen dem Dienst und dem STS.  
  
## <a name="rp-feb-2005-and-sts-feb-2005"></a>RP (Feb.&#160;2005) und STS (Feb.&#160;2005)  
 Die WSDL für die abhängige Seite (Relying Party, RP) enthält im `RequestSecurityTokenTemplate`-Abschnitt die folgenden Elemente:  
  
-   `CanonicalizationAlgorithm`  
  
-   `EncryptionAlgorithm`  
  
-   `EncryptWith`  
  
-   `SignWith`  
  
-   `KeySize`  
  
-   `KeyType`  
  
 Die Clientkonfigurationsdatei enthält eine Liste mit Parametern.  
  
 WCF kann nicht zwischen Client und Dienst unterscheiden; Es fügt alle Parameter und sendet sie in der `RequestSecurityTokenTemplate` (RST).  
  
## <a name="rp-trust-13-and-sts-trust-13"></a>RP Trust&#160;1.3 und STS Trust&#160;1.3  
 Die WSDL für RP enthält im `RequestSecurityTokenTemplate`-Abschnitt die folgenden Elemente:  
  
-   `CanonicalizationAlgorithm`  
  
-   `EncryptionAlgorithm`  
  
-   `EncryptWith`  
  
-   `SignWith`  
  
-   `KeySize`  
  
-   `KeyType`  
  
-   `KeyWrapAlgorithm`  
  
 Die Clientkonfigurationsdatei enthält ein `secondaryParameters`-Element, das die von der RP angegebenen Parameter umschließt.  
  
 WCF entfernt die `EncryptionAlgorithm`, `CanonicalizationAlgorithm` und `KeyWrapAlgorithm` Elemente aus dem Element oberster Ebene, unter dem RST, sofern dies in vorhanden sind die `SecondaryParameters` Element. Fügt WCF die `SecondaryParameters` Element Änderungen an das ausgehende RST.  
  
## <a name="rp-trust-feb-2005-and-sts-trust-13"></a>RP Trust (Feb.&#160;2005) und STS Trust&#160;1.3  
 Die WSDL für RP enthält im `RequestSecurityTokenTemplate`-Abschnitt die folgenden Elemente:  
  
-   `CanonicalizationAlgorithm`  
  
-   `EncryptionAlgorithm`  
  
-   `EncryptWith`  
  
-   `SignWith`  
  
-   `KeySize`  
  
-   `KeyType`  
  
 Die Clientkonfigurationsdatei enthält eine Liste mit Parametern.  
  
 Aus der Clientkonfigurationsdatei kann nicht WCF zwischen Dienst und Client unterschieden. WCF konvertiert daher alle Parameter in einen Trust-Version 1.3-Namespace an.  
  
 WCF verarbeitet die `KeyType`, `KeySize`, und `TokenType` Elemente wie folgt:  
  
-   Laden Sie die WSDL herunter, erstellen Sie die Bindung, und weisen Sie `KeyType`, `KeySize` und `TokenType` auf Basis der RP-Parameter zu. Anschließend wird die Clientkonfigurationsdatei generiert.  
  
-   Der Client kann nun jeden Parameter in der Konfigurationsdatei ändern.  
  
-   Während der Laufzeit-WCF kopiert alle angegebenen Parameter in der `AdditionalTokenParameters` Abschnitt der Konfigurationsdatei des Clients mit Ausnahme von `KeyType`, `KeySize` und `TokenType`, da diese Parameter während der Konfigurationsdatei berücksichtigt werden die Generierung.  
  
## <a name="rp-trust-13-and-sts-trust-feb-2005"></a>RP Trust&#160;1.3 und STS Trust (Feb.&#160;2005)  
 Die WSDL für RP enthält im `RequestSecurityTokenTemplate`-Abschnitt die folgenden Elemente:  
  
-   `CanonicalizationAlgorithm`  
  
-   `EncryptionAlgorithm`  
  
-   `EncryptWith`  
  
-   `SignWith`  
  
-   `KeySize`  
  
-   `KeyType`  
  
-   `KeyWrapAlgorithm`  
  
 Die Clientkonfigurationsdatei enthält ein `secondaryParamters`-Element, das die von der RP angegebenen Parameter umschließt.  
  
 WCF kopiert alle Parameter angegeben wird, innerhalb der `SecondaryParameters` Abschnitt aus, um das RST-Element der obersten Ebene, jedoch nicht auf der sie in der 2005-WS-Trust-Namespace konvertiert werden.

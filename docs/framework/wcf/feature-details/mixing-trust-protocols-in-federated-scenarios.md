---
title: Verwenden mehrerer verschiedener Vertrauensprotokolle in Verbundszenarien
ms.date: 03/30/2017
ms.assetid: d7b5fee9-2246-4b09-b8d7-9e63cb817279
ms.openlocfilehash: 5ce178c0b2c83469a26993ce6db2d6c87815543b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96248174"
---
# <a name="mixing-trust-protocols-in-federated-scenarios"></a>Verwenden mehrerer verschiedener Vertrauensprotokolle in Verbundszenarien

Unter bestimmten Bedingungen sind Szenarios denkbar, in denen Verbundclients mit einem Dienst und mit einem Security Token Service (STS) kommunizieren, die nicht die gleiche Trust-Version besitzen. Die Dienst-WSDL kann eine `RequestSecurityTokenTemplate`-Assertion mit WS-Trust-Elementen enthalten, die aus anderen Versionen stammen als der STS. In solchen Fällen konvertiert ein Windows Communication Foundation (WCF)-Client die WS-Trust Elemente, die von empfangen werden `RequestSecurityTokenTemplate` , damit Sie der STS-Vertrauensstellungs Version entsprechen. WCF verarbeitet nicht übereinstimmende Trust-Versionen nur für Standard Bindungen. Alle Standardalgorithmusparameter, die von WCF erkannt werden, sind Teil der Standard Bindung. In diesem Thema wird das WCF-Verhalten mit verschiedenen Vertrauens Einstellungen zwischen dem Dienst und dem STS beschrieben.  
  
## <a name="rp-feb-2005-and-sts-feb-2005"></a>RP (Feb.&#160;2005) und STS (Feb.&#160;2005)  

 Die WSDL für die abhängige Seite (Relying Party, RP) enthält im `RequestSecurityTokenTemplate`-Abschnitt die folgenden Elemente:  
  
- `CanonicalizationAlgorithm`  
  
- `EncryptionAlgorithm`  
  
- `EncryptWith`  
  
- `SignWith`  
  
- `KeySize`  
  
- `KeyType`  
  
 Die Clientkonfigurationsdatei enthält eine Liste mit Parametern.  
  
 WCF kann nicht zwischen Client-und Dienst Parametern unterscheiden. Sie fügt alle Parameter hinzu und sendet Sie in der `RequestSecurityTokenTemplate` (RST).  
  
## <a name="rp-trust-13-and-sts-trust-13"></a>RP Trust&#160;1.3 und STS Trust&#160;1.3  

 Die WSDL für RP enthält im `RequestSecurityTokenTemplate`-Abschnitt die folgenden Elemente:  
  
- `CanonicalizationAlgorithm`  
  
- `EncryptionAlgorithm`  
  
- `EncryptWith`  
  
- `SignWith`  
  
- `KeySize`  
  
- `KeyType`  
  
- `KeyWrapAlgorithm`  
  
 Die Clientkonfigurationsdatei enthält ein `secondaryParameters`-Element, das die von der RP angegebenen Parameter umschließt.  
  
 WCF entfernt das `EncryptionAlgorithm` `CanonicalizationAlgorithm` -Element, das-Element und das- `KeyWrapAlgorithm` Element aus dem Element der obersten Ebene unter dem RST, sofern diese innerhalb des-Elements vorhanden sind `SecondaryParameters` . WCF fügt das- `SecondaryParameters` Element unverändert an das ausgehende RST an.  
  
## <a name="rp-trust-feb-2005-and-sts-trust-13"></a>RP Trust (Feb.&#160;2005) und STS Trust&#160;1.3  

 Die WSDL für RP enthält im `RequestSecurityTokenTemplate`-Abschnitt die folgenden Elemente:  
  
- `CanonicalizationAlgorithm`  
  
- `EncryptionAlgorithm`  
  
- `EncryptWith`  
  
- `SignWith`  
  
- `KeySize`  
  
- `KeyType`  
  
 Die Clientkonfigurationsdatei enthält eine Liste mit Parametern.  
  
 In der Client Konfigurationsdatei kann WCF nicht zwischen Dienst-und Client Parametern unterscheiden. Daher konvertiert WCF alle Parameter in einen Trust Version 1,3-Namespace.  
  
 WCF verarbeitet die `KeyType` `KeySize` Elemente, und `TokenType` wie folgt:  
  
- Laden Sie die WSDL herunter, erstellen Sie die Bindung, und weisen Sie `KeyType`, `KeySize` und `TokenType` auf Basis der RP-Parameter zu. Anschließend wird die Clientkonfigurationsdatei generiert.  
  
- Der Client kann nun jeden Parameter in der Konfigurationsdatei ändern.  
  
- Während der Laufzeit kopiert WCF alle Parameter, die in den `AdditionalTokenParameters` -Abschnitt der Client Konfigurationsdatei angegeben sind, mit Ausnahme von `KeyType` , `KeySize` und `TokenType` , da diese Parameter während der Generierung der Konfigurationsdatei berücksichtigt werden.  
  
## <a name="rp-trust-13-and-sts-trust-feb-2005"></a>RP Trust&#160;1.3 und STS Trust (Feb.&#160;2005)  

 Die WSDL für RP enthält im `RequestSecurityTokenTemplate`-Abschnitt die folgenden Elemente:  
  
- `CanonicalizationAlgorithm`  
  
- `EncryptionAlgorithm`  
  
- `EncryptWith`  
  
- `SignWith`  
  
- `KeySize`  
  
- `KeyType`  
  
- `KeyWrapAlgorithm`  
  
 Die Clientkonfigurationsdatei enthält ein `secondaryParamters`-Element, das die von der RP angegebenen Parameter umschließt.  
  
 WCF kopiert alle Parameter, die im- `SecondaryParameters` Abschnitt angegeben sind, in das RST-Element der obersten Ebene, konvertiert sie jedoch nicht in den 2005-WS-Trust Namespace.

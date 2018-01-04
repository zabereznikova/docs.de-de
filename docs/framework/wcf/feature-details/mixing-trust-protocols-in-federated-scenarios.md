---
title: Verwenden mehrerer verschiedener Vertrauensprotokolle in Verbundszenarien
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d7b5fee9-2246-4b09-b8d7-9e63cb817279
caps.latest.revision: "7"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 7031e222b152bfa61e13e0e4a44b5ad9418b07c9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="mixing-trust-protocols-in-federated-scenarios"></a>Verwenden mehrerer verschiedener Vertrauensprotokolle in Verbundszenarien
Unter bestimmten Bedingungen sind Szenarios denkbar, in denen Verbundclients mit einem Dienst und mit einem Security Token Service (STS) kommunizieren, die nicht die gleiche Trust-Version besitzen. Die Dienst-WSDL kann eine `RequestSecurityTokenTemplate`-Assertion mit WS-Trust-Elementen enthalten, die aus anderen Versionen stammen als der STS. In solchen Fällen konvertiert ein [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Client die aus `RequestSecurityTokenTemplate` empfangenen WS-Trust-Elemente, damit Sie der STS-Trust-Version entsprechen. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] behandelt nicht übereinstimmende Trust-Versionen nur für Standardbindungen. Alle Standardalgorithmusparameter, die von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] erkannt werden, sind Teil der Standardbindung. In diesem Thema wird das [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Verhalten mit verschiedenen Vertrauenseinstellungen zwischen dem Dienst und dem STS beschrieben.  
  
## <a name="rp-feb-2005-and-sts-feb-2005"></a>RP (Feb.&#160;2005) und STS (Feb.&#160;2005)  
 Die WSDL für die abhängige Seite (Relying Party, RP) enthält im `RequestSecurityTokenTemplate`-Abschnitt die folgenden Elemente:  
  
-   `CanonicalizationAlgorithm`  
  
-   `EncryptionAlgorithm`  
  
-   `EncryptWith`  
  
-   `SignWith`  
  
-   `KeySize`  
  
-   `KeyType`  
  
 Die Clientkonfigurationsdatei enthält eine Liste mit Parametern.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] unterscheidet nicht zwischen Client- und Dienstparametern, also werden alle Parameter hinzugefügt und in der `RequestSecurityTokenTemplate` (RST) versendet.  
  
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
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] entfernt das `EncryptionAlgorithm`-Element, das `CanonicalizationAlgorithm`-Element und das `KeyWrapAlgorithm`-Element aus dem Element oberster Ebene unter dem RST, sofern diese innerhalb des `SecondaryParameters`-Elements vorhanden sind. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] hängt das `SecondaryParameters`-Element ohne Änderungen an das ausgehende RST an.  
  
## <a name="rp-trust-feb-2005-and-sts-trust-13"></a>RP Trust (Feb.&#160;2005) und STS Trust&#160;1.3  
 Die WSDL für RP enthält im `RequestSecurityTokenTemplate`-Abschnitt die folgenden Elemente:  
  
-   `CanonicalizationAlgorithm`  
  
-   `EncryptionAlgorithm`  
  
-   `EncryptWith`  
  
-   `SignWith`  
  
-   `KeySize`  
  
-   `KeyType`  
  
 Die Clientkonfigurationsdatei enthält eine Liste mit Parametern.  
  
 Anhand der Clientkonfigurationsdatei kann [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] nicht zwischen Dienst- und Clientparametern unterscheiden. Deshalb konvertiert [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] alle Parameter in einen Trust&#160;1.3-Namespace.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] behandelt das `KeyType`-Element, das `KeySize`-Element und das `TokenType`-Element folgendermaßen:  
  
-   Laden Sie die WSDL herunter, erstellen Sie die Bindung, und weisen Sie `KeyType`, `KeySize` und `TokenType` auf Basis der RP-Parameter zu. Anschließend wird die Clientkonfigurationsdatei generiert.  
  
-   Der Client kann nun jeden Parameter in der Konfigurationsdatei ändern.  
  
-   Zur Laufzeit kopiert [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] alle angegebenen Parameter in den `AdditionalTokenParameters`-Abschnitt der Konfigurationsdatei. Hiervon ausgenommen sind `KeyType`, `KeySize` und `TokenType`, da diese Parameter beim Generieren der Konfigurationsdatei berücksichtigt werden.  
  
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
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] kopiert alle Parameter, die im `SecondaryParameters`-Abschnitt angegeben sind, in das RST-Element oberster Ebene, die Parameter werden jedoch nicht in den WS-Trust-Namespace&#160;(2005) konvertiert.

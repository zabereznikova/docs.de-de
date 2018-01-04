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
# <a name="mixing-trust-protocols-in-federated-scenarios"></a><span data-ttu-id="7484a-102">Verwenden mehrerer verschiedener Vertrauensprotokolle in Verbundszenarien</span><span class="sxs-lookup"><span data-stu-id="7484a-102">Mixing Trust Protocols in Federated Scenarios</span></span>
<span data-ttu-id="7484a-103">Unter bestimmten Bedingungen sind Szenarios denkbar, in denen Verbundclients mit einem Dienst und mit einem Security Token Service (STS) kommunizieren, die nicht die gleiche Trust-Version besitzen.</span><span class="sxs-lookup"><span data-stu-id="7484a-103">There may be scenarios in which federated clients communicate with a service and a Security Token Service (STS) that do not have the same trust version.</span></span> <span data-ttu-id="7484a-104">Die Dienst-WSDL kann eine `RequestSecurityTokenTemplate`-Assertion mit WS-Trust-Elementen enthalten, die aus anderen Versionen stammen als der STS.</span><span class="sxs-lookup"><span data-stu-id="7484a-104">The service WSDL can contain a `RequestSecurityTokenTemplate` assertion with WS-Trust elements that are of different versions than the STS.</span></span> <span data-ttu-id="7484a-105">In solchen Fällen konvertiert ein [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Client die aus `RequestSecurityTokenTemplate` empfangenen WS-Trust-Elemente, damit Sie der STS-Trust-Version entsprechen.</span><span class="sxs-lookup"><span data-stu-id="7484a-105">In such cases, a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] client converts the WS-Trust elements received from the `RequestSecurityTokenTemplate` to match the STS trust version.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="7484a-106"> behandelt nicht übereinstimmende Trust-Versionen nur für Standardbindungen.</span><span class="sxs-lookup"><span data-stu-id="7484a-106"> handles mismatched trust versions only for standard bindings.</span></span> <span data-ttu-id="7484a-107">Alle Standardalgorithmusparameter, die von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] erkannt werden, sind Teil der Standardbindung.</span><span class="sxs-lookup"><span data-stu-id="7484a-107">All standard algorithm parameters that are recognized by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] are part of the standard binding.</span></span> <span data-ttu-id="7484a-108">In diesem Thema wird das [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Verhalten mit verschiedenen Vertrauenseinstellungen zwischen dem Dienst und dem STS beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7484a-108">This topic describes the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] behavior with various trust settings between the service and the STS.</span></span>  
  
## <a name="rp-feb-2005-and-sts-feb-2005"></a><span data-ttu-id="7484a-109">RP (Feb.&#160;2005) und STS (Feb.&#160;2005)</span><span class="sxs-lookup"><span data-stu-id="7484a-109">RP Feb 2005 and STS Feb 2005</span></span>  
 <span data-ttu-id="7484a-110">Die WSDL für die abhängige Seite (Relying Party, RP) enthält im `RequestSecurityTokenTemplate`-Abschnitt die folgenden Elemente:</span><span class="sxs-lookup"><span data-stu-id="7484a-110">The WSDL for Relying Party (RP) contains the following elements within the `RequestSecurityTokenTemplate` section:</span></span>  
  
-   `CanonicalizationAlgorithm`  
  
-   `EncryptionAlgorithm`  
  
-   `EncryptWith`  
  
-   `SignWith`  
  
-   `KeySize`  
  
-   `KeyType`  
  
 <span data-ttu-id="7484a-111">Die Clientkonfigurationsdatei enthält eine Liste mit Parametern.</span><span class="sxs-lookup"><span data-stu-id="7484a-111">The client configuration file contains a list of parameters.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="7484a-112"> unterscheidet nicht zwischen Client- und Dienstparametern, also werden alle Parameter hinzugefügt und in der `RequestSecurityTokenTemplate` (RST) versendet.</span><span class="sxs-lookup"><span data-stu-id="7484a-112"> cannot differentiate between the client and service parameters; it adds all the parameters and sends them in the `RequestSecurityTokenTemplate` (RST).</span></span>  
  
## <a name="rp-trust-13-and-sts-trust-13"></a><span data-ttu-id="7484a-113">RP Trust&#160;1.3 und STS Trust&#160;1.3</span><span class="sxs-lookup"><span data-stu-id="7484a-113">RP Trust 1.3 and STS Trust 1.3</span></span>  
 <span data-ttu-id="7484a-114">Die WSDL für RP enthält im `RequestSecurityTokenTemplate`-Abschnitt die folgenden Elemente:</span><span class="sxs-lookup"><span data-stu-id="7484a-114">The WSDL for RP contains the following elements within the `RequestSecurityTokenTemplate` section:</span></span>  
  
-   `CanonicalizationAlgorithm`  
  
-   `EncryptionAlgorithm`  
  
-   `EncryptWith`  
  
-   `SignWith`  
  
-   `KeySize`  
  
-   `KeyType`  
  
-   `KeyWrapAlgorithm`  
  
 <span data-ttu-id="7484a-115">Die Clientkonfigurationsdatei enthält ein `secondaryParameters`-Element, das die von der RP angegebenen Parameter umschließt.</span><span class="sxs-lookup"><span data-stu-id="7484a-115">The client configuration file contains a `secondaryParameters` element that wraps the parameters specified by the RP.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="7484a-116"> entfernt das `EncryptionAlgorithm`-Element, das `CanonicalizationAlgorithm`-Element und das `KeyWrapAlgorithm`-Element aus dem Element oberster Ebene unter dem RST, sofern diese innerhalb des `SecondaryParameters`-Elements vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="7484a-116"> removes the `EncryptionAlgorithm`, `CanonicalizationAlgorithm` and `KeyWrapAlgorithm` elements from the top-level element under the RST if these are present inside the `SecondaryParameters` element.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="7484a-117"> hängt das `SecondaryParameters`-Element ohne Änderungen an das ausgehende RST an.</span><span class="sxs-lookup"><span data-stu-id="7484a-117"> appends the `SecondaryParameters` element to the outgoing RST unmodified.</span></span>  
  
## <a name="rp-trust-feb-2005-and-sts-trust-13"></a><span data-ttu-id="7484a-118">RP Trust (Feb.&#160;2005) und STS Trust&#160;1.3</span><span class="sxs-lookup"><span data-stu-id="7484a-118">RP Trust Feb 2005 and STS Trust 1.3</span></span>  
 <span data-ttu-id="7484a-119">Die WSDL für RP enthält im `RequestSecurityTokenTemplate`-Abschnitt die folgenden Elemente:</span><span class="sxs-lookup"><span data-stu-id="7484a-119">The WSDL for RP contains the following elements in the `RequestSecurityTokenTemplate` section:</span></span>  
  
-   `CanonicalizationAlgorithm`  
  
-   `EncryptionAlgorithm`  
  
-   `EncryptWith`  
  
-   `SignWith`  
  
-   `KeySize`  
  
-   `KeyType`  
  
 <span data-ttu-id="7484a-120">Die Clientkonfigurationsdatei enthält eine Liste mit Parametern.</span><span class="sxs-lookup"><span data-stu-id="7484a-120">The client configuration file contains a list of parameters.</span></span>  
  
 <span data-ttu-id="7484a-121">Anhand der Clientkonfigurationsdatei kann [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] nicht zwischen Dienst- und Clientparametern unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="7484a-121">From the client configuration file, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] cannot differentiate between the service and client parameters.</span></span> <span data-ttu-id="7484a-122">Deshalb konvertiert [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] alle Parameter in einen Trust&#160;1.3-Namespace.</span><span class="sxs-lookup"><span data-stu-id="7484a-122">Therefore [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] converts all the parameters to a Trust version 1.3 namespace.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="7484a-123"> behandelt das `KeyType`-Element, das `KeySize`-Element und das `TokenType`-Element folgendermaßen:</span><span class="sxs-lookup"><span data-stu-id="7484a-123"> handles the `KeyType`, `KeySize`, and `TokenType` elements as follows:</span></span>  
  
-   <span data-ttu-id="7484a-124">Laden Sie die WSDL herunter, erstellen Sie die Bindung, und weisen Sie `KeyType`, `KeySize` und `TokenType` auf Basis der RP-Parameter zu.</span><span class="sxs-lookup"><span data-stu-id="7484a-124">Download the WSDL, create the binding, and assign `KeyType`, `KeySize`, and `TokenType` from the RP parameters.</span></span> <span data-ttu-id="7484a-125">Anschließend wird die Clientkonfigurationsdatei generiert.</span><span class="sxs-lookup"><span data-stu-id="7484a-125">The client configuration file is then generated.</span></span>  
  
-   <span data-ttu-id="7484a-126">Der Client kann nun jeden Parameter in der Konfigurationsdatei ändern.</span><span class="sxs-lookup"><span data-stu-id="7484a-126">The client can now change any parameter in the configuration file.</span></span>  
  
-   <span data-ttu-id="7484a-127">Zur Laufzeit kopiert [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] alle angegebenen Parameter in den `AdditionalTokenParameters`-Abschnitt der Konfigurationsdatei. Hiervon ausgenommen sind `KeyType`, `KeySize` und `TokenType`, da diese Parameter beim Generieren der Konfigurationsdatei berücksichtigt werden.</span><span class="sxs-lookup"><span data-stu-id="7484a-127">During runtime, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] copies all parameters specified into the `AdditionalTokenParameters` section of the client configuration file except `KeyType`, `KeySize` and `TokenType`, because these parameters are accounted for during the configuration file generation.</span></span>  
  
## <a name="rp-trust-13-and-sts-trust-feb-2005"></a><span data-ttu-id="7484a-128">RP Trust&#160;1.3 und STS Trust (Feb.&#160;2005)</span><span class="sxs-lookup"><span data-stu-id="7484a-128">RP Trust 1.3 and STS Trust Feb 2005</span></span>  
 <span data-ttu-id="7484a-129">Die WSDL für RP enthält im `RequestSecurityTokenTemplate`-Abschnitt die folgenden Elemente:</span><span class="sxs-lookup"><span data-stu-id="7484a-129">The WSDL for RP contains the following elements in the `RequestSecurityTokenTemplate` section:</span></span>  
  
-   `CanonicalizationAlgorithm`  
  
-   `EncryptionAlgorithm`  
  
-   `EncryptWith`  
  
-   `SignWith`  
  
-   `KeySize`  
  
-   `KeyType`  
  
-   `KeyWrapAlgorithm`  
  
 <span data-ttu-id="7484a-130">Die Clientkonfigurationsdatei enthält ein `secondaryParamters`-Element, das die von der RP angegebenen Parameter umschließt.</span><span class="sxs-lookup"><span data-stu-id="7484a-130">The client configuration file contains a `secondaryParamters` element that wraps the parameters specified by the RP.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="7484a-131"> kopiert alle Parameter, die im `SecondaryParameters`-Abschnitt angegeben sind, in das RST-Element oberster Ebene, die Parameter werden jedoch nicht in den WS-Trust-Namespace&#160;(2005) konvertiert.</span><span class="sxs-lookup"><span data-stu-id="7484a-131"> copies all the parameters specified within the `SecondaryParameters` section to the top-level RST element, but does not convert them to the 2005 WS-Trust namespace.</span></span>

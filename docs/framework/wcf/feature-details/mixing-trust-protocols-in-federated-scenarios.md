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
# <a name="mixing-trust-protocols-in-federated-scenarios"></a><span data-ttu-id="9aec9-102">Verwenden mehrerer verschiedener Vertrauensprotokolle in Verbundszenarien</span><span class="sxs-lookup"><span data-stu-id="9aec9-102">Mixing Trust Protocols in Federated Scenarios</span></span>

<span data-ttu-id="9aec9-103">Unter bestimmten Bedingungen sind Szenarios denkbar, in denen Verbundclients mit einem Dienst und mit einem Security Token Service (STS) kommunizieren, die nicht die gleiche Trust-Version besitzen.</span><span class="sxs-lookup"><span data-stu-id="9aec9-103">There may be scenarios in which federated clients communicate with a service and a Security Token Service (STS) that do not have the same trust version.</span></span> <span data-ttu-id="9aec9-104">Die Dienst-WSDL kann eine `RequestSecurityTokenTemplate`-Assertion mit WS-Trust-Elementen enthalten, die aus anderen Versionen stammen als der STS.</span><span class="sxs-lookup"><span data-stu-id="9aec9-104">The service WSDL can contain a `RequestSecurityTokenTemplate` assertion with WS-Trust elements that are of different versions than the STS.</span></span> <span data-ttu-id="9aec9-105">In solchen Fällen konvertiert ein Windows Communication Foundation (WCF)-Client die WS-Trust Elemente, die von empfangen werden `RequestSecurityTokenTemplate` , damit Sie der STS-Vertrauensstellungs Version entsprechen.</span><span class="sxs-lookup"><span data-stu-id="9aec9-105">In such cases, a Windows Communication Foundation (WCF) client converts the WS-Trust elements received from the `RequestSecurityTokenTemplate` to match the STS trust version.</span></span> <span data-ttu-id="9aec9-106">WCF verarbeitet nicht übereinstimmende Trust-Versionen nur für Standard Bindungen.</span><span class="sxs-lookup"><span data-stu-id="9aec9-106">WCF handles mismatched trust versions only for standard bindings.</span></span> <span data-ttu-id="9aec9-107">Alle Standardalgorithmusparameter, die von WCF erkannt werden, sind Teil der Standard Bindung.</span><span class="sxs-lookup"><span data-stu-id="9aec9-107">All standard algorithm parameters that are recognized by WCF are part of the standard binding.</span></span> <span data-ttu-id="9aec9-108">In diesem Thema wird das WCF-Verhalten mit verschiedenen Vertrauens Einstellungen zwischen dem Dienst und dem STS beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9aec9-108">This topic describes the WCF behavior with various trust settings between the service and the STS.</span></span>  
  
## <a name="rp-feb-2005-and-sts-feb-2005"></a><span data-ttu-id="9aec9-109">RP (Feb.&#160;2005) und STS (Feb.&#160;2005)</span><span class="sxs-lookup"><span data-stu-id="9aec9-109">RP Feb 2005 and STS Feb 2005</span></span>  

 <span data-ttu-id="9aec9-110">Die WSDL für die abhängige Seite (Relying Party, RP) enthält im `RequestSecurityTokenTemplate`-Abschnitt die folgenden Elemente:</span><span class="sxs-lookup"><span data-stu-id="9aec9-110">The WSDL for Relying Party (RP) contains the following elements within the `RequestSecurityTokenTemplate` section:</span></span>  
  
- `CanonicalizationAlgorithm`  
  
- `EncryptionAlgorithm`  
  
- `EncryptWith`  
  
- `SignWith`  
  
- `KeySize`  
  
- `KeyType`  
  
 <span data-ttu-id="9aec9-111">Die Clientkonfigurationsdatei enthält eine Liste mit Parametern.</span><span class="sxs-lookup"><span data-stu-id="9aec9-111">The client configuration file contains a list of parameters.</span></span>  
  
 <span data-ttu-id="9aec9-112">WCF kann nicht zwischen Client-und Dienst Parametern unterscheiden. Sie fügt alle Parameter hinzu und sendet Sie in der `RequestSecurityTokenTemplate` (RST).</span><span class="sxs-lookup"><span data-stu-id="9aec9-112">WCF cannot differentiate between the client and service parameters; it adds all the parameters and sends them in the `RequestSecurityTokenTemplate` (RST).</span></span>  
  
## <a name="rp-trust-13-and-sts-trust-13"></a><span data-ttu-id="9aec9-113">RP Trust&#160;1.3 und STS Trust&#160;1.3</span><span class="sxs-lookup"><span data-stu-id="9aec9-113">RP Trust 1.3 and STS Trust 1.3</span></span>  

 <span data-ttu-id="9aec9-114">Die WSDL für RP enthält im `RequestSecurityTokenTemplate`-Abschnitt die folgenden Elemente:</span><span class="sxs-lookup"><span data-stu-id="9aec9-114">The WSDL for RP contains the following elements within the `RequestSecurityTokenTemplate` section:</span></span>  
  
- `CanonicalizationAlgorithm`  
  
- `EncryptionAlgorithm`  
  
- `EncryptWith`  
  
- `SignWith`  
  
- `KeySize`  
  
- `KeyType`  
  
- `KeyWrapAlgorithm`  
  
 <span data-ttu-id="9aec9-115">Die Clientkonfigurationsdatei enthält ein `secondaryParameters`-Element, das die von der RP angegebenen Parameter umschließt.</span><span class="sxs-lookup"><span data-stu-id="9aec9-115">The client configuration file contains a `secondaryParameters` element that wraps the parameters specified by the RP.</span></span>  
  
 <span data-ttu-id="9aec9-116">WCF entfernt das `EncryptionAlgorithm` `CanonicalizationAlgorithm` -Element, das-Element und das- `KeyWrapAlgorithm` Element aus dem Element der obersten Ebene unter dem RST, sofern diese innerhalb des-Elements vorhanden sind `SecondaryParameters` .</span><span class="sxs-lookup"><span data-stu-id="9aec9-116">WCF removes the `EncryptionAlgorithm`, `CanonicalizationAlgorithm` and `KeyWrapAlgorithm` elements from the top-level element under the RST if these are present inside the `SecondaryParameters` element.</span></span> <span data-ttu-id="9aec9-117">WCF fügt das- `SecondaryParameters` Element unverändert an das ausgehende RST an.</span><span class="sxs-lookup"><span data-stu-id="9aec9-117">WCF appends the `SecondaryParameters` element to the outgoing RST unmodified.</span></span>  
  
## <a name="rp-trust-feb-2005-and-sts-trust-13"></a><span data-ttu-id="9aec9-118">RP Trust (Feb.&#160;2005) und STS Trust&#160;1.3</span><span class="sxs-lookup"><span data-stu-id="9aec9-118">RP Trust Feb 2005 and STS Trust 1.3</span></span>  

 <span data-ttu-id="9aec9-119">Die WSDL für RP enthält im `RequestSecurityTokenTemplate`-Abschnitt die folgenden Elemente:</span><span class="sxs-lookup"><span data-stu-id="9aec9-119">The WSDL for RP contains the following elements in the `RequestSecurityTokenTemplate` section:</span></span>  
  
- `CanonicalizationAlgorithm`  
  
- `EncryptionAlgorithm`  
  
- `EncryptWith`  
  
- `SignWith`  
  
- `KeySize`  
  
- `KeyType`  
  
 <span data-ttu-id="9aec9-120">Die Clientkonfigurationsdatei enthält eine Liste mit Parametern.</span><span class="sxs-lookup"><span data-stu-id="9aec9-120">The client configuration file contains a list of parameters.</span></span>  
  
 <span data-ttu-id="9aec9-121">In der Client Konfigurationsdatei kann WCF nicht zwischen Dienst-und Client Parametern unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="9aec9-121">From the client configuration file, WCF cannot differentiate between the service and client parameters.</span></span> <span data-ttu-id="9aec9-122">Daher konvertiert WCF alle Parameter in einen Trust Version 1,3-Namespace.</span><span class="sxs-lookup"><span data-stu-id="9aec9-122">Therefore WCF converts all the parameters to a Trust version 1.3 namespace.</span></span>  
  
 <span data-ttu-id="9aec9-123">WCF verarbeitet die `KeyType` `KeySize` Elemente, und `TokenType` wie folgt:</span><span class="sxs-lookup"><span data-stu-id="9aec9-123">WCF handles the `KeyType`, `KeySize`, and `TokenType` elements as follows:</span></span>  
  
- <span data-ttu-id="9aec9-124">Laden Sie die WSDL herunter, erstellen Sie die Bindung, und weisen Sie `KeyType`, `KeySize` und `TokenType` auf Basis der RP-Parameter zu.</span><span class="sxs-lookup"><span data-stu-id="9aec9-124">Download the WSDL, create the binding, and assign `KeyType`, `KeySize`, and `TokenType` from the RP parameters.</span></span> <span data-ttu-id="9aec9-125">Anschließend wird die Clientkonfigurationsdatei generiert.</span><span class="sxs-lookup"><span data-stu-id="9aec9-125">The client configuration file is then generated.</span></span>  
  
- <span data-ttu-id="9aec9-126">Der Client kann nun jeden Parameter in der Konfigurationsdatei ändern.</span><span class="sxs-lookup"><span data-stu-id="9aec9-126">The client can now change any parameter in the configuration file.</span></span>  
  
- <span data-ttu-id="9aec9-127">Während der Laufzeit kopiert WCF alle Parameter, die in den `AdditionalTokenParameters` -Abschnitt der Client Konfigurationsdatei angegeben sind, mit Ausnahme von `KeyType` , `KeySize` und `TokenType` , da diese Parameter während der Generierung der Konfigurationsdatei berücksichtigt werden.</span><span class="sxs-lookup"><span data-stu-id="9aec9-127">During runtime, WCF copies all parameters specified into the `AdditionalTokenParameters` section of the client configuration file except `KeyType`, `KeySize` and `TokenType`, because these parameters are accounted for during the configuration file generation.</span></span>  
  
## <a name="rp-trust-13-and-sts-trust-feb-2005"></a><span data-ttu-id="9aec9-128">RP Trust&#160;1.3 und STS Trust (Feb.&#160;2005)</span><span class="sxs-lookup"><span data-stu-id="9aec9-128">RP Trust 1.3 and STS Trust Feb 2005</span></span>  

 <span data-ttu-id="9aec9-129">Die WSDL für RP enthält im `RequestSecurityTokenTemplate`-Abschnitt die folgenden Elemente:</span><span class="sxs-lookup"><span data-stu-id="9aec9-129">The WSDL for RP contains the following elements in the `RequestSecurityTokenTemplate` section:</span></span>  
  
- `CanonicalizationAlgorithm`  
  
- `EncryptionAlgorithm`  
  
- `EncryptWith`  
  
- `SignWith`  
  
- `KeySize`  
  
- `KeyType`  
  
- `KeyWrapAlgorithm`  
  
 <span data-ttu-id="9aec9-130">Die Clientkonfigurationsdatei enthält ein `secondaryParamters`-Element, das die von der RP angegebenen Parameter umschließt.</span><span class="sxs-lookup"><span data-stu-id="9aec9-130">The client configuration file contains a `secondaryParamters` element that wraps the parameters specified by the RP.</span></span>  
  
 <span data-ttu-id="9aec9-131">WCF kopiert alle Parameter, die im- `SecondaryParameters` Abschnitt angegeben sind, in das RST-Element der obersten Ebene, konvertiert sie jedoch nicht in den 2005-WS-Trust Namespace.</span><span class="sxs-lookup"><span data-stu-id="9aec9-131">WCF copies all the parameters specified within the `SecondaryParameters` section to the top-level RST element, but does not convert them to the 2005 WS-Trust namespace.</span></span>

---
title: Verwenden mehrerer verschiedener Vertrauensprotokolle in Verbundszenarien
ms.date: 03/30/2017
ms.assetid: d7b5fee9-2246-4b09-b8d7-9e63cb817279
author: BrucePerlerMS
ms.openlocfilehash: d4290880d8d708811a95b38356aa61f0d23c89a8
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/06/2018
ms.locfileid: "48842501"
---
# <a name="mixing-trust-protocols-in-federated-scenarios"></a><span data-ttu-id="55272-102">Verwenden mehrerer verschiedener Vertrauensprotokolle in Verbundszenarien</span><span class="sxs-lookup"><span data-stu-id="55272-102">Mixing Trust Protocols in Federated Scenarios</span></span>
<span data-ttu-id="55272-103">Unter bestimmten Bedingungen sind Szenarios denkbar, in denen Verbundclients mit einem Dienst und mit einem Security Token Service (STS) kommunizieren, die nicht die gleiche Trust-Version besitzen.</span><span class="sxs-lookup"><span data-stu-id="55272-103">There may be scenarios in which federated clients communicate with a service and a Security Token Service (STS) that do not have the same trust version.</span></span> <span data-ttu-id="55272-104">Die Dienst-WSDL kann eine `RequestSecurityTokenTemplate`-Assertion mit WS-Trust-Elementen enthalten, die aus anderen Versionen stammen als der STS.</span><span class="sxs-lookup"><span data-stu-id="55272-104">The service WSDL can contain a `RequestSecurityTokenTemplate` assertion with WS-Trust elements that are of different versions than the STS.</span></span> <span data-ttu-id="55272-105">In solchen Fällen konvertiert ein Windows Communication Foundation (WCF)-Client die WS-Trust-Elemente aus der `RequestSecurityTokenTemplate` entsprechend der STS-trust-Version.</span><span class="sxs-lookup"><span data-stu-id="55272-105">In such cases, a Windows Communication Foundation (WCF) client converts the WS-Trust elements received from the `RequestSecurityTokenTemplate` to match the STS trust version.</span></span> <span data-ttu-id="55272-106">WCF behandelt nicht übereinstimmende Trust-Versionen nur für standardbindungen.</span><span class="sxs-lookup"><span data-stu-id="55272-106">WCF handles mismatched trust versions only for standard bindings.</span></span> <span data-ttu-id="55272-107">Alle standardalgorithmusparameter, die von WCF erkannt werden, sind Teil der standardbindung.</span><span class="sxs-lookup"><span data-stu-id="55272-107">All standard algorithm parameters that are recognized by WCF are part of the standard binding.</span></span> <span data-ttu-id="55272-108">In diesem Thema wird beschrieben, die WCF-Verhalten mit verschiedenen vertrauenseinstellungen zwischen dem Dienst und dem STS.</span><span class="sxs-lookup"><span data-stu-id="55272-108">This topic describes the WCF behavior with various trust settings between the service and the STS.</span></span>  
  
## <a name="rp-feb-2005-and-sts-feb-2005"></a><span data-ttu-id="55272-109">RP (Feb.&#160;2005) und STS (Feb.&#160;2005)</span><span class="sxs-lookup"><span data-stu-id="55272-109">RP Feb 2005 and STS Feb 2005</span></span>  
 <span data-ttu-id="55272-110">Die WSDL für die abhängige Seite (Relying Party, RP) enthält im `RequestSecurityTokenTemplate`-Abschnitt die folgenden Elemente:</span><span class="sxs-lookup"><span data-stu-id="55272-110">The WSDL for Relying Party (RP) contains the following elements within the `RequestSecurityTokenTemplate` section:</span></span>  
  
-   `CanonicalizationAlgorithm`  
  
-   `EncryptionAlgorithm`  
  
-   `EncryptWith`  
  
-   `SignWith`  
  
-   `KeySize`  
  
-   `KeyType`  
  
 <span data-ttu-id="55272-111">Die Clientkonfigurationsdatei enthält eine Liste mit Parametern.</span><span class="sxs-lookup"><span data-stu-id="55272-111">The client configuration file contains a list of parameters.</span></span>  
  
 <span data-ttu-id="55272-112">WCF kann nicht zwischen Client und Dienst unterscheiden; Es fügt alle Parameter und sendet sie in der `RequestSecurityTokenTemplate` (RST).</span><span class="sxs-lookup"><span data-stu-id="55272-112">WCF cannot differentiate between the client and service parameters; it adds all the parameters and sends them in the `RequestSecurityTokenTemplate` (RST).</span></span>  
  
## <a name="rp-trust-13-and-sts-trust-13"></a><span data-ttu-id="55272-113">RP Trust&#160;1.3 und STS Trust&#160;1.3</span><span class="sxs-lookup"><span data-stu-id="55272-113">RP Trust 1.3 and STS Trust 1.3</span></span>  
 <span data-ttu-id="55272-114">Die WSDL für RP enthält im `RequestSecurityTokenTemplate`-Abschnitt die folgenden Elemente:</span><span class="sxs-lookup"><span data-stu-id="55272-114">The WSDL for RP contains the following elements within the `RequestSecurityTokenTemplate` section:</span></span>  
  
-   `CanonicalizationAlgorithm`  
  
-   `EncryptionAlgorithm`  
  
-   `EncryptWith`  
  
-   `SignWith`  
  
-   `KeySize`  
  
-   `KeyType`  
  
-   `KeyWrapAlgorithm`  
  
 <span data-ttu-id="55272-115">Die Clientkonfigurationsdatei enthält ein `secondaryParameters`-Element, das die von der RP angegebenen Parameter umschließt.</span><span class="sxs-lookup"><span data-stu-id="55272-115">The client configuration file contains a `secondaryParameters` element that wraps the parameters specified by the RP.</span></span>  
  
 <span data-ttu-id="55272-116">WCF entfernt die `EncryptionAlgorithm`, `CanonicalizationAlgorithm` und `KeyWrapAlgorithm` Elemente aus dem Element oberster Ebene, unter dem RST, sofern dies in vorhanden sind die `SecondaryParameters` Element.</span><span class="sxs-lookup"><span data-stu-id="55272-116">WCF removes the `EncryptionAlgorithm`, `CanonicalizationAlgorithm` and `KeyWrapAlgorithm` elements from the top-level element under the RST if these are present inside the `SecondaryParameters` element.</span></span> <span data-ttu-id="55272-117">Fügt WCF die `SecondaryParameters` Element Änderungen an das ausgehende RST.</span><span class="sxs-lookup"><span data-stu-id="55272-117">WCF appends the `SecondaryParameters` element to the outgoing RST unmodified.</span></span>  
  
## <a name="rp-trust-feb-2005-and-sts-trust-13"></a><span data-ttu-id="55272-118">RP Trust (Feb.&#160;2005) und STS Trust&#160;1.3</span><span class="sxs-lookup"><span data-stu-id="55272-118">RP Trust Feb 2005 and STS Trust 1.3</span></span>  
 <span data-ttu-id="55272-119">Die WSDL für RP enthält im `RequestSecurityTokenTemplate`-Abschnitt die folgenden Elemente:</span><span class="sxs-lookup"><span data-stu-id="55272-119">The WSDL for RP contains the following elements in the `RequestSecurityTokenTemplate` section:</span></span>  
  
-   `CanonicalizationAlgorithm`  
  
-   `EncryptionAlgorithm`  
  
-   `EncryptWith`  
  
-   `SignWith`  
  
-   `KeySize`  
  
-   `KeyType`  
  
 <span data-ttu-id="55272-120">Die Clientkonfigurationsdatei enthält eine Liste mit Parametern.</span><span class="sxs-lookup"><span data-stu-id="55272-120">The client configuration file contains a list of parameters.</span></span>  
  
 <span data-ttu-id="55272-121">Aus der Clientkonfigurationsdatei kann nicht WCF zwischen Dienst und Client unterschieden.</span><span class="sxs-lookup"><span data-stu-id="55272-121">From the client configuration file, WCF cannot differentiate between the service and client parameters.</span></span> <span data-ttu-id="55272-122">WCF konvertiert daher alle Parameter in einen Trust-Version 1.3-Namespace an.</span><span class="sxs-lookup"><span data-stu-id="55272-122">Therefore WCF converts all the parameters to a Trust version 1.3 namespace.</span></span>  
  
 <span data-ttu-id="55272-123">WCF verarbeitet die `KeyType`, `KeySize`, und `TokenType` Elemente wie folgt:</span><span class="sxs-lookup"><span data-stu-id="55272-123">WCF handles the `KeyType`, `KeySize`, and `TokenType` elements as follows:</span></span>  
  
-   <span data-ttu-id="55272-124">Laden Sie die WSDL herunter, erstellen Sie die Bindung, und weisen Sie `KeyType`, `KeySize` und `TokenType` auf Basis der RP-Parameter zu.</span><span class="sxs-lookup"><span data-stu-id="55272-124">Download the WSDL, create the binding, and assign `KeyType`, `KeySize`, and `TokenType` from the RP parameters.</span></span> <span data-ttu-id="55272-125">Anschließend wird die Clientkonfigurationsdatei generiert.</span><span class="sxs-lookup"><span data-stu-id="55272-125">The client configuration file is then generated.</span></span>  
  
-   <span data-ttu-id="55272-126">Der Client kann nun jeden Parameter in der Konfigurationsdatei ändern.</span><span class="sxs-lookup"><span data-stu-id="55272-126">The client can now change any parameter in the configuration file.</span></span>  
  
-   <span data-ttu-id="55272-127">Während der Laufzeit-WCF kopiert alle angegebenen Parameter in der `AdditionalTokenParameters` Abschnitt der Konfigurationsdatei des Clients mit Ausnahme von `KeyType`, `KeySize` und `TokenType`, da diese Parameter während der Konfigurationsdatei berücksichtigt werden die Generierung.</span><span class="sxs-lookup"><span data-stu-id="55272-127">During runtime, WCF copies all parameters specified into the `AdditionalTokenParameters` section of the client configuration file except `KeyType`, `KeySize` and `TokenType`, because these parameters are accounted for during the configuration file generation.</span></span>  
  
## <a name="rp-trust-13-and-sts-trust-feb-2005"></a><span data-ttu-id="55272-128">RP Trust&#160;1.3 und STS Trust (Feb.&#160;2005)</span><span class="sxs-lookup"><span data-stu-id="55272-128">RP Trust 1.3 and STS Trust Feb 2005</span></span>  
 <span data-ttu-id="55272-129">Die WSDL für RP enthält im `RequestSecurityTokenTemplate`-Abschnitt die folgenden Elemente:</span><span class="sxs-lookup"><span data-stu-id="55272-129">The WSDL for RP contains the following elements in the `RequestSecurityTokenTemplate` section:</span></span>  
  
-   `CanonicalizationAlgorithm`  
  
-   `EncryptionAlgorithm`  
  
-   `EncryptWith`  
  
-   `SignWith`  
  
-   `KeySize`  
  
-   `KeyType`  
  
-   `KeyWrapAlgorithm`  
  
 <span data-ttu-id="55272-130">Die Clientkonfigurationsdatei enthält ein `secondaryParamters`-Element, das die von der RP angegebenen Parameter umschließt.</span><span class="sxs-lookup"><span data-stu-id="55272-130">The client configuration file contains a `secondaryParamters` element that wraps the parameters specified by the RP.</span></span>  
  
 <span data-ttu-id="55272-131">WCF kopiert alle Parameter angegeben wird, innerhalb der `SecondaryParameters` Abschnitt aus, um das RST-Element der obersten Ebene, jedoch nicht auf der sie in der 2005-WS-Trust-Namespace konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="55272-131">WCF copies all the parameters specified within the `SecondaryParameters` section to the top-level RST element, but does not convert them to the 2005 WS-Trust namespace.</span></span>

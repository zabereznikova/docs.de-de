---
title: TransactionFlowBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0a9656fe-2400-45ca-ad79-92715c8cf190
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: fa5394e874e35b80b01796642e18d69c71e867dc
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="transactionflowbindingelement"></a><span data-ttu-id="17c10-102">TransactionFlowBindingElement</span><span class="sxs-lookup"><span data-stu-id="17c10-102">TransactionFlowBindingElement</span></span>
<span data-ttu-id="17c10-103">TransactionFlowBindingElement</span><span class="sxs-lookup"><span data-stu-id="17c10-103">TransactionFlowBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17c10-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="17c10-104">Syntax</span></span>  
  
```  
class TransactionFlowBindingElement : BindingElement  
{  
  string IssuedTokens;  
  string TransactionProtocol;  
  boolean Transactions;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="17c10-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="17c10-105">Methods</span></span>  
 <span data-ttu-id="17c10-106">Von der TransactionFlowBindingElement-Klasse werden keine Methoden definiert.</span><span class="sxs-lookup"><span data-stu-id="17c10-106">The TransactionFlowBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="17c10-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="17c10-107">Properties</span></span>  
 <span data-ttu-id="17c10-108">Die TransactionFlowBindingElement-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="17c10-108">The TransactionFlowBindingElement class has the following properties:</span></span>  
  
### <a name="issuedtokens"></a><span data-ttu-id="17c10-109">IssuedTokens</span><span class="sxs-lookup"><span data-stu-id="17c10-109">IssuedTokens</span></span>  
 <span data-ttu-id="17c10-110">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="17c10-110">Data type: string</span></span>  
  
 <span data-ttu-id="17c10-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="17c10-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="17c10-112">Gibt die Anforderung für einen ausgegebenen Sicherheitstoken-Header (IssuedTokens von WS-Trust) an.</span><span class="sxs-lookup"><span data-stu-id="17c10-112">Specifies the requirement for an issued security tokens header (IssuedTokens from WS-Trust).</span></span>  
  
### <a name="transactionprotocol"></a><span data-ttu-id="17c10-113">TransactionProtocol</span><span class="sxs-lookup"><span data-stu-id="17c10-113">TransactionProtocol</span></span>  
 <span data-ttu-id="17c10-114">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="17c10-114">Data type: string</span></span>  
  
 <span data-ttu-id="17c10-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="17c10-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="17c10-116">Das vom Dienst für den Transaktionsfluss verwendete Transaktionsprotokoll.</span><span class="sxs-lookup"><span data-stu-id="17c10-116">The transactions protocol used by the service to flow transactions.</span></span>  
  
### <a name="transactions"></a><span data-ttu-id="17c10-117">Transaktionen</span><span class="sxs-lookup"><span data-stu-id="17c10-117">Transactions</span></span>  
 <span data-ttu-id="17c10-118">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="17c10-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="17c10-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="17c10-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="17c10-120">Gibt an, ob die eingehende Transaktion unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="17c10-120">Indicates whether the incoming transaction is supported.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="17c10-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="17c10-121">Requirements</span></span>  
  
|<span data-ttu-id="17c10-122">MOF</span><span class="sxs-lookup"><span data-stu-id="17c10-122">MOF</span></span>|<span data-ttu-id="17c10-123">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="17c10-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="17c10-124">Namespace</span><span class="sxs-lookup"><span data-stu-id="17c10-124">Namespace</span></span>|<span data-ttu-id="17c10-125">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="17c10-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="17c10-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="17c10-126">See Also</span></span>  
 <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>

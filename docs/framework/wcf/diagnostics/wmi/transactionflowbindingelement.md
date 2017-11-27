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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4c65eb1689d1411cb9083967b9a29c946b7568b7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="transactionflowbindingelement"></a><span data-ttu-id="cf150-102">TransactionFlowBindingElement</span><span class="sxs-lookup"><span data-stu-id="cf150-102">TransactionFlowBindingElement</span></span>
<span data-ttu-id="cf150-103">TransactionFlowBindingElement</span><span class="sxs-lookup"><span data-stu-id="cf150-103">TransactionFlowBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf150-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cf150-104">Syntax</span></span>  
  
```  
class TransactionFlowBindingElement : BindingElement  
{  
  string IssuedTokens;  
  string TransactionProtocol;  
  boolean Transactions;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="cf150-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="cf150-105">Methods</span></span>  
 <span data-ttu-id="cf150-106">Von der TransactionFlowBindingElement-Klasse werden keine Methoden definiert.</span><span class="sxs-lookup"><span data-stu-id="cf150-106">The TransactionFlowBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="cf150-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="cf150-107">Properties</span></span>  
 <span data-ttu-id="cf150-108">Die TransactionFlowBindingElement-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="cf150-108">The TransactionFlowBindingElement class has the following properties:</span></span>  
  
### <a name="issuedtokens"></a><span data-ttu-id="cf150-109">IssuedTokens</span><span class="sxs-lookup"><span data-stu-id="cf150-109">IssuedTokens</span></span>  
 <span data-ttu-id="cf150-110">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="cf150-110">Data type: string</span></span>  
  
 <span data-ttu-id="cf150-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="cf150-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="cf150-112">Gibt die Anforderung für einen ausgegebenen Sicherheitstoken-Header (IssuedTokens von WS-Trust) an.</span><span class="sxs-lookup"><span data-stu-id="cf150-112">Specifies the requirement for an issued security tokens header (IssuedTokens from WS-Trust).</span></span>  
  
### <a name="transactionprotocol"></a><span data-ttu-id="cf150-113">TransactionProtocol</span><span class="sxs-lookup"><span data-stu-id="cf150-113">TransactionProtocol</span></span>  
 <span data-ttu-id="cf150-114">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="cf150-114">Data type: string</span></span>  
  
 <span data-ttu-id="cf150-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="cf150-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="cf150-116">Das vom Dienst für den Transaktionsfluss verwendete Transaktionsprotokoll.</span><span class="sxs-lookup"><span data-stu-id="cf150-116">The transactions protocol used by the service to flow transactions.</span></span>  
  
### <a name="transactions"></a><span data-ttu-id="cf150-117">Transaktionen</span><span class="sxs-lookup"><span data-stu-id="cf150-117">Transactions</span></span>  
 <span data-ttu-id="cf150-118">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="cf150-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="cf150-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="cf150-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="cf150-120">Gibt an, ob die eingehende Transaktion unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="cf150-120">Indicates whether the incoming transaction is supported.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf150-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cf150-121">Requirements</span></span>  
  
|<span data-ttu-id="cf150-122">MOF</span><span class="sxs-lookup"><span data-stu-id="cf150-122">MOF</span></span>|<span data-ttu-id="cf150-123">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="cf150-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="cf150-124">Namespace</span><span class="sxs-lookup"><span data-stu-id="cf150-124">Namespace</span></span>|<span data-ttu-id="cf150-125">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="cf150-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cf150-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cf150-126">See Also</span></span>  
 <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>

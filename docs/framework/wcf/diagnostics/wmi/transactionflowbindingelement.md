---
title: TransactionFlowBindingElement
ms.date: 03/30/2017
ms.assetid: 0a9656fe-2400-45ca-ad79-92715c8cf190
ms.openlocfilehash: d0311837ebb8112d9492fb548492bcd3e10230e7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54514569"
---
# <a name="transactionflowbindingelement"></a><span data-ttu-id="789e9-102">TransactionFlowBindingElement</span><span class="sxs-lookup"><span data-stu-id="789e9-102">TransactionFlowBindingElement</span></span>
<span data-ttu-id="789e9-103">TransactionFlowBindingElement</span><span class="sxs-lookup"><span data-stu-id="789e9-103">TransactionFlowBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="789e9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="789e9-104">Syntax</span></span>  
  
```csharp
class TransactionFlowBindingElement : BindingElement  
{  
  string IssuedTokens;  
  string TransactionProtocol;  
  boolean Transactions;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="789e9-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="789e9-105">Methods</span></span>  
 <span data-ttu-id="789e9-106">Von der TransactionFlowBindingElement-Klasse werden keine Methoden definiert.</span><span class="sxs-lookup"><span data-stu-id="789e9-106">The TransactionFlowBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="789e9-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="789e9-107">Properties</span></span>  
 <span data-ttu-id="789e9-108">Die TransactionFlowBindingElement-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="789e9-108">The TransactionFlowBindingElement class has the following properties:</span></span>  
  
### <a name="issuedtokens"></a><span data-ttu-id="789e9-109">IssuedTokens</span><span class="sxs-lookup"><span data-stu-id="789e9-109">IssuedTokens</span></span>  
 <span data-ttu-id="789e9-110">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="789e9-110">Data type: string</span></span>  
  
 <span data-ttu-id="789e9-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="789e9-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="789e9-112">Gibt die Anforderung für einen ausgegebenen Sicherheitstoken-Header (IssuedTokens von WS-Trust) an.</span><span class="sxs-lookup"><span data-stu-id="789e9-112">Specifies the requirement for an issued security tokens header (IssuedTokens from WS-Trust).</span></span>  
  
### <a name="transactionprotocol"></a><span data-ttu-id="789e9-113">TransactionProtocol</span><span class="sxs-lookup"><span data-stu-id="789e9-113">TransactionProtocol</span></span>  
 <span data-ttu-id="789e9-114">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="789e9-114">Data type: string</span></span>  
  
 <span data-ttu-id="789e9-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="789e9-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="789e9-116">Das vom Dienst für den Transaktionsfluss verwendete Transaktionsprotokoll.</span><span class="sxs-lookup"><span data-stu-id="789e9-116">The transactions protocol used by the service to flow transactions.</span></span>  
  
### <a name="transactions"></a><span data-ttu-id="789e9-117">Transaktionen</span><span class="sxs-lookup"><span data-stu-id="789e9-117">Transactions</span></span>  
 <span data-ttu-id="789e9-118">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="789e9-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="789e9-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="789e9-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="789e9-120">Gibt an, ob die eingehende Transaktion unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="789e9-120">Indicates whether the incoming transaction is supported.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="789e9-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="789e9-121">Requirements</span></span>  
  
|<span data-ttu-id="789e9-122">MOF</span><span class="sxs-lookup"><span data-stu-id="789e9-122">MOF</span></span>|<span data-ttu-id="789e9-123">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="789e9-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="789e9-124">Namespace</span><span class="sxs-lookup"><span data-stu-id="789e9-124">Namespace</span></span>|<span data-ttu-id="789e9-125">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="789e9-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="789e9-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="789e9-126">See also</span></span>
- <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>

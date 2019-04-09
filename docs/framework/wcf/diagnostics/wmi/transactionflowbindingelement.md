---
title: TransactionFlowBindingElement
ms.date: 03/30/2017
ms.assetid: 0a9656fe-2400-45ca-ad79-92715c8cf190
ms.openlocfilehash: a58d5620abbb636480ceea3020552246ae284842
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59150084"
---
# <a name="transactionflowbindingelement"></a><span data-ttu-id="a7800-102">TransactionFlowBindingElement</span><span class="sxs-lookup"><span data-stu-id="a7800-102">TransactionFlowBindingElement</span></span>
<span data-ttu-id="a7800-103">TransactionFlowBindingElement</span><span class="sxs-lookup"><span data-stu-id="a7800-103">TransactionFlowBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7800-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a7800-104">Syntax</span></span>  
  
```csharp
class TransactionFlowBindingElement : BindingElement  
{  
  string IssuedTokens;  
  string TransactionProtocol;  
  boolean Transactions;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="a7800-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="a7800-105">Methods</span></span>  
 <span data-ttu-id="a7800-106">Von der TransactionFlowBindingElement-Klasse werden keine Methoden definiert.</span><span class="sxs-lookup"><span data-stu-id="a7800-106">The TransactionFlowBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="a7800-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="a7800-107">Properties</span></span>  
 <span data-ttu-id="a7800-108">Die TransactionFlowBindingElement-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="a7800-108">The TransactionFlowBindingElement class has the following properties:</span></span>  
  
### <a name="issuedtokens"></a><span data-ttu-id="a7800-109">IssuedTokens</span><span class="sxs-lookup"><span data-stu-id="a7800-109">IssuedTokens</span></span>  
 <span data-ttu-id="a7800-110">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="a7800-110">Data type: string</span></span>  
  
 <span data-ttu-id="a7800-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="a7800-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a7800-112">Gibt die Anforderung für einen ausgegebenen Sicherheitstoken-Header (IssuedTokens von WS-Trust) an.</span><span class="sxs-lookup"><span data-stu-id="a7800-112">Specifies the requirement for an issued security tokens header (IssuedTokens from WS-Trust).</span></span>  
  
### <a name="transactionprotocol"></a><span data-ttu-id="a7800-113">TransactionProtocol</span><span class="sxs-lookup"><span data-stu-id="a7800-113">TransactionProtocol</span></span>  
 <span data-ttu-id="a7800-114">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="a7800-114">Data type: string</span></span>  
  
 <span data-ttu-id="a7800-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="a7800-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a7800-116">Das vom Dienst für den Transaktionsfluss verwendete Transaktionsprotokoll.</span><span class="sxs-lookup"><span data-stu-id="a7800-116">The transactions protocol used by the service to flow transactions.</span></span>  
  
### <a name="transactions"></a><span data-ttu-id="a7800-117">Transaktionen</span><span class="sxs-lookup"><span data-stu-id="a7800-117">Transactions</span></span>  
 <span data-ttu-id="a7800-118">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="a7800-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="a7800-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="a7800-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a7800-120">Gibt an, ob die eingehende Transaktion unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="a7800-120">Indicates whether the incoming transaction is supported.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7800-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a7800-121">Requirements</span></span>  
  
|<span data-ttu-id="a7800-122">MOF</span><span class="sxs-lookup"><span data-stu-id="a7800-122">MOF</span></span>|<span data-ttu-id="a7800-123">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="a7800-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="a7800-124">Namespace</span><span class="sxs-lookup"><span data-stu-id="a7800-124">Namespace</span></span>|<span data-ttu-id="a7800-125">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="a7800-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a7800-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a7800-126">See also</span></span>

- <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>

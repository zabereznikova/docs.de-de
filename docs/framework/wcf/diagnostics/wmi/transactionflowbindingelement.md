---
title: TransactionFlowBindingElement
ms.date: 03/30/2017
ms.assetid: 0a9656fe-2400-45ca-ad79-92715c8cf190
ms.openlocfilehash: a58d5620abbb636480ceea3020552246ae284842
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59771594"
---
# <a name="transactionflowbindingelement"></a><span data-ttu-id="37127-102">TransactionFlowBindingElement</span><span class="sxs-lookup"><span data-stu-id="37127-102">TransactionFlowBindingElement</span></span>
<span data-ttu-id="37127-103">TransactionFlowBindingElement</span><span class="sxs-lookup"><span data-stu-id="37127-103">TransactionFlowBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37127-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="37127-104">Syntax</span></span>  
  
```csharp
class TransactionFlowBindingElement : BindingElement  
{  
  string IssuedTokens;  
  string TransactionProtocol;  
  boolean Transactions;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="37127-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="37127-105">Methods</span></span>  
 <span data-ttu-id="37127-106">Von der TransactionFlowBindingElement-Klasse werden keine Methoden definiert.</span><span class="sxs-lookup"><span data-stu-id="37127-106">The TransactionFlowBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="37127-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="37127-107">Properties</span></span>  
 <span data-ttu-id="37127-108">Die TransactionFlowBindingElement-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="37127-108">The TransactionFlowBindingElement class has the following properties:</span></span>  
  
### <a name="issuedtokens"></a><span data-ttu-id="37127-109">IssuedTokens</span><span class="sxs-lookup"><span data-stu-id="37127-109">IssuedTokens</span></span>  
 <span data-ttu-id="37127-110">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="37127-110">Data type: string</span></span>  
  
 <span data-ttu-id="37127-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="37127-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="37127-112">Gibt die Anforderung für einen ausgegebenen Sicherheitstoken-Header (IssuedTokens von WS-Trust) an.</span><span class="sxs-lookup"><span data-stu-id="37127-112">Specifies the requirement for an issued security tokens header (IssuedTokens from WS-Trust).</span></span>  
  
### <a name="transactionprotocol"></a><span data-ttu-id="37127-113">TransactionProtocol</span><span class="sxs-lookup"><span data-stu-id="37127-113">TransactionProtocol</span></span>  
 <span data-ttu-id="37127-114">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="37127-114">Data type: string</span></span>  
  
 <span data-ttu-id="37127-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="37127-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="37127-116">Das vom Dienst für den Transaktionsfluss verwendete Transaktionsprotokoll.</span><span class="sxs-lookup"><span data-stu-id="37127-116">The transactions protocol used by the service to flow transactions.</span></span>  
  
### <a name="transactions"></a><span data-ttu-id="37127-117">Transaktionen</span><span class="sxs-lookup"><span data-stu-id="37127-117">Transactions</span></span>  
 <span data-ttu-id="37127-118">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="37127-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="37127-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="37127-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="37127-120">Gibt an, ob die eingehende Transaktion unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="37127-120">Indicates whether the incoming transaction is supported.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="37127-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="37127-121">Requirements</span></span>  
  
|<span data-ttu-id="37127-122">MOF</span><span class="sxs-lookup"><span data-stu-id="37127-122">MOF</span></span>|<span data-ttu-id="37127-123">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="37127-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="37127-124">Namespace</span><span class="sxs-lookup"><span data-stu-id="37127-124">Namespace</span></span>|<span data-ttu-id="37127-125">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="37127-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="37127-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="37127-126">See also</span></span>

- <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>

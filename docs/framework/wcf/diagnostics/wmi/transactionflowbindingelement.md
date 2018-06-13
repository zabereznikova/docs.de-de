---
title: TransactionFlowBindingElement
ms.date: 03/30/2017
ms.assetid: 0a9656fe-2400-45ca-ad79-92715c8cf190
ms.openlocfilehash: c2fb32c4c693cbfc487ce89b36f013398cbdb703
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33485618"
---
# <a name="transactionflowbindingelement"></a><span data-ttu-id="c616b-102">TransactionFlowBindingElement</span><span class="sxs-lookup"><span data-stu-id="c616b-102">TransactionFlowBindingElement</span></span>
<span data-ttu-id="c616b-103">TransactionFlowBindingElement</span><span class="sxs-lookup"><span data-stu-id="c616b-103">TransactionFlowBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c616b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c616b-104">Syntax</span></span>  
  
```  
class TransactionFlowBindingElement : BindingElement  
{  
  string IssuedTokens;  
  string TransactionProtocol;  
  boolean Transactions;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="c616b-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="c616b-105">Methods</span></span>  
 <span data-ttu-id="c616b-106">Von der TransactionFlowBindingElement-Klasse werden keine Methoden definiert.</span><span class="sxs-lookup"><span data-stu-id="c616b-106">The TransactionFlowBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="c616b-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="c616b-107">Properties</span></span>  
 <span data-ttu-id="c616b-108">Die TransactionFlowBindingElement-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="c616b-108">The TransactionFlowBindingElement class has the following properties:</span></span>  
  
### <a name="issuedtokens"></a><span data-ttu-id="c616b-109">IssuedTokens</span><span class="sxs-lookup"><span data-stu-id="c616b-109">IssuedTokens</span></span>  
 <span data-ttu-id="c616b-110">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="c616b-110">Data type: string</span></span>  
  
 <span data-ttu-id="c616b-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="c616b-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c616b-112">Gibt die Anforderung für einen ausgegebenen Sicherheitstoken-Header (IssuedTokens von WS-Trust) an.</span><span class="sxs-lookup"><span data-stu-id="c616b-112">Specifies the requirement for an issued security tokens header (IssuedTokens from WS-Trust).</span></span>  
  
### <a name="transactionprotocol"></a><span data-ttu-id="c616b-113">TransactionProtocol</span><span class="sxs-lookup"><span data-stu-id="c616b-113">TransactionProtocol</span></span>  
 <span data-ttu-id="c616b-114">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="c616b-114">Data type: string</span></span>  
  
 <span data-ttu-id="c616b-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="c616b-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c616b-116">Das vom Dienst für den Transaktionsfluss verwendete Transaktionsprotokoll.</span><span class="sxs-lookup"><span data-stu-id="c616b-116">The transactions protocol used by the service to flow transactions.</span></span>  
  
### <a name="transactions"></a><span data-ttu-id="c616b-117">Transaktionen</span><span class="sxs-lookup"><span data-stu-id="c616b-117">Transactions</span></span>  
 <span data-ttu-id="c616b-118">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="c616b-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="c616b-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="c616b-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c616b-120">Gibt an, ob die eingehende Transaktion unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="c616b-120">Indicates whether the incoming transaction is supported.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c616b-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c616b-121">Requirements</span></span>  
  
|<span data-ttu-id="c616b-122">MOF</span><span class="sxs-lookup"><span data-stu-id="c616b-122">MOF</span></span>|<span data-ttu-id="c616b-123">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="c616b-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="c616b-124">Namespace</span><span class="sxs-lookup"><span data-stu-id="c616b-124">Namespace</span></span>|<span data-ttu-id="c616b-125">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="c616b-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c616b-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c616b-126">See Also</span></span>  
 <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>

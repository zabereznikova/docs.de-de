---
title: TransactionFlowBindingElement
ms.date: 03/30/2017
ms.assetid: 0a9656fe-2400-45ca-ad79-92715c8cf190
ms.openlocfilehash: 577502d1cd3d81784cb9b1eb3b249376b8ffa6b8
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96234894"
---
# <a name="transactionflowbindingelement"></a><span data-ttu-id="2d8d7-102">TransactionFlowBindingElement</span><span class="sxs-lookup"><span data-stu-id="2d8d7-102">TransactionFlowBindingElement</span></span>

<span data-ttu-id="2d8d7-103">TransactionFlowBindingElement</span><span class="sxs-lookup"><span data-stu-id="2d8d7-103">TransactionFlowBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d8d7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2d8d7-104">Syntax</span></span>  
  
```csharp
class TransactionFlowBindingElement : BindingElement  
{  
  string IssuedTokens;  
  string TransactionProtocol;  
  boolean Transactions;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="2d8d7-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="2d8d7-105">Methods</span></span>  

 <span data-ttu-id="2d8d7-106">Von der TransactionFlowBindingElement-Klasse werden keine Methoden definiert.</span><span class="sxs-lookup"><span data-stu-id="2d8d7-106">The TransactionFlowBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="2d8d7-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="2d8d7-107">Properties</span></span>  

 <span data-ttu-id="2d8d7-108">Die TransactionFlowBindingElement-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="2d8d7-108">The TransactionFlowBindingElement class has the following properties:</span></span>  
  
### <a name="issuedtokens"></a><span data-ttu-id="2d8d7-109">IssuedTokens</span><span class="sxs-lookup"><span data-stu-id="2d8d7-109">IssuedTokens</span></span>  

 <span data-ttu-id="2d8d7-110">Datentyp: String</span><span class="sxs-lookup"><span data-stu-id="2d8d7-110">Data type: string</span></span>  
  
 <span data-ttu-id="2d8d7-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="2d8d7-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2d8d7-112">Gibt die Anforderung für einen ausgegebenen Sicherheitstoken-Header (IssuedTokens von WS-Trust) an.</span><span class="sxs-lookup"><span data-stu-id="2d8d7-112">Specifies the requirement for an issued security tokens header (IssuedTokens from WS-Trust).</span></span>  
  
### <a name="transactionprotocol"></a><span data-ttu-id="2d8d7-113">TransactionProtocol</span><span class="sxs-lookup"><span data-stu-id="2d8d7-113">TransactionProtocol</span></span>  

 <span data-ttu-id="2d8d7-114">Datentyp: String</span><span class="sxs-lookup"><span data-stu-id="2d8d7-114">Data type: string</span></span>  
  
 <span data-ttu-id="2d8d7-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="2d8d7-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2d8d7-116">Das vom Dienst für den Transaktionsfluss verwendete Transaktionsprotokoll.</span><span class="sxs-lookup"><span data-stu-id="2d8d7-116">The transactions protocol used by the service to flow transactions.</span></span>  
  
### <a name="transactions"></a><span data-ttu-id="2d8d7-117">Transaktionen</span><span class="sxs-lookup"><span data-stu-id="2d8d7-117">Transactions</span></span>  

 <span data-ttu-id="2d8d7-118">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="2d8d7-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="2d8d7-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="2d8d7-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2d8d7-120">Gibt an, ob die eingehende Transaktion unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="2d8d7-120">Indicates whether the incoming transaction is supported.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d8d7-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2d8d7-121">Requirements</span></span>  
  
|<span data-ttu-id="2d8d7-122">MOF</span><span class="sxs-lookup"><span data-stu-id="2d8d7-122">MOF</span></span>|<span data-ttu-id="2d8d7-123">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="2d8d7-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="2d8d7-124">Namespace</span><span class="sxs-lookup"><span data-stu-id="2d8d7-124">Namespace</span></span>|<span data-ttu-id="2d8d7-125">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="2d8d7-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2d8d7-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2d8d7-126">See also</span></span>

- <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>

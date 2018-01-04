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
ms.workload: dotnet
ms.openlocfilehash: 0b073efc47ccc1708bf4c58153b1001a21eee25f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="transactionflowbindingelement"></a>TransactionFlowBindingElement
TransactionFlowBindingElement  
  
## <a name="syntax"></a>Syntax  
  
```  
class TransactionFlowBindingElement : BindingElement  
{  
  string IssuedTokens;  
  string TransactionProtocol;  
  boolean Transactions;  
};  
```  
  
## <a name="methods"></a>Methoden  
 Von der TransactionFlowBindingElement-Klasse werden keine Methoden definiert.  
  
## <a name="properties"></a>Eigenschaften  
 Die TransactionFlowBindingElement-Klasse verfügt über die folgenden Eigenschaften:  
  
### <a name="issuedtokens"></a>IssuedTokens  
 Datentyp: string (Zeichenfolge)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Gibt die Anforderung für einen ausgegebenen Sicherheitstoken-Header (IssuedTokens von WS-Trust) an.  
  
### <a name="transactionprotocol"></a>TransactionProtocol  
 Datentyp: string (Zeichenfolge)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Das vom Dienst für den Transaktionsfluss verwendete Transaktionsprotokoll.  
  
### <a name="transactions"></a>Transaktionen  
 Datentyp: Boolesch  
  
 Zugriffstyp: Schreibgeschützt  
  
 Gibt an, ob die eingehende Transaktion unterstützt wird.  
  
## <a name="requirements"></a>Anforderungen  
  
|MOF|Deklariert in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Namespace|Definiert in root\ServiceModel|  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>

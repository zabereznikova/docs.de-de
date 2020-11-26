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
# <a name="transactionflowbindingelement"></a>TransactionFlowBindingElement

TransactionFlowBindingElement  
  
## <a name="syntax"></a>Syntax  
  
```csharp
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

 Datentyp: String  
  
 Zugriffstyp: Schreibgeschützt  
  
 Gibt die Anforderung für einen ausgegebenen Sicherheitstoken-Header (IssuedTokens von WS-Trust) an.  
  
### <a name="transactionprotocol"></a>TransactionProtocol  

 Datentyp: String  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>

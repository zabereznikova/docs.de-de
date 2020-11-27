---
title: Transaktionsausnahmen
ms.date: 03/30/2017
ms.assetid: 1d27ed51-7eda-477f-9eca-94fa129f3e07
ms.openlocfilehash: dcdf825699368617335f2d59a05f8826884a8e9e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96285680"
---
# <a name="transaction-exceptions"></a>Transaktionsausnahmen

In diesem Thema werden alle Ausnahmen aufgelistet, die von Windows Communication Foundation (WCF)-Transaktion generiert werden.  
  
## <a name="exception-list"></a>Ausnahmeliste  
  
|Ressourcencode|Ressourcenzeichenfolge|  
|-------------------|---------------------|  
|SFxCannotHaveDifferentTransactionProtocolsInOneBinding|Die Richtlinieninformationen, die von Metadaten importiert werden, geben andere Werte für TransactionProtocol unter den Vorgängen an. Nur ein einziges TransactionProtocol für jeden Endpunkt wird unterstützt.|  
|SFxTransactionAutoCompleteFalseAndInstanceContextMode|TransactionAutoComplete kann den Wert "false" nicht annehmen, es sei denn, der InstanceContextMode des Diensts ist PerSession. Bei der Implementierung des festgelegten Vertrags und Vorgangs wurde ein Fehler gefunden.|  
|SFxTransactionInvalidSetTransactionComplete|OperationContext.SetTransactionComplete kann nur in einem Vorgang aufgerufen werden, wenn TransactionAutoComplete auf "false" und TransactionScopeRequired auf "true" stehen. Dies ist ein ungültiges Szenario, und die aktuelle Transaktion wurde beendet.|  
|TransactionFlowRequiredIssuedTokens|Um eine Transaktion auszuführen, muss das Ausführen von ausgestellten Token unterstützt werden.|  
|TrustDriverVersionDoesNotSupportIssuedTokens|Die konfigurierte Trust-Version unterstützt keine ausgestellten Token. Verwenden Sie WSTrustFeb2005 oder höher.|

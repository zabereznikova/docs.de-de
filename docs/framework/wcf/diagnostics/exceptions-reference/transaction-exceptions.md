---
title: Transaktionsausnahmen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1d27ed51-7eda-477f-9eca-94fa129f3e07
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: be53af47aef4d42ddd2c77fbd29c8c9e9961c47b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="transaction-exceptions"></a>Transaktionsausnahmen
In diesem Thema werden alle Ausnahmen aufgelistet, die von der [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]-Transaktion generiert werden.  
  
## <a name="exception-list"></a>Ausnahmeliste  
  
|Ressourcencode|Ressourcenzeichenfolge|  
|-------------------|---------------------|  
|SFxCannotHaveDifferentTransactionProtocolsInOneBinding|Die Richtlinieninformationen, die von Metadaten importiert werden, geben andere Werte für TransactionProtocol unter den Vorgängen an. Nur ein einziges TransactionProtocol für jeden Endpunkt wird unterstützt.|  
|SFxTransactionAutoCompleteFalseAndInstanceContextMode|TransactionAutoComplete kann den Wert "false" nicht annehmen, es sei denn, der InstanceContextMode des Diensts ist PerSession. Bei der Implementierung des festgelegten Vertrags und Vorgangs wurde ein Fehler gefunden.|  
|SFxTransactionInvalidSetTransactionComplete|OperationContext.SetTransactionComplete kann nur in einem Vorgang aufgerufen werden, wenn TransactionAutoComplete auf "false" und TransactionScopeRequired auf "true" stehen. Dies ist ein ungültiges Szenario, und die aktuelle Transaktion wurde beendet.|  
|TransactionFlowRequiredIssuedTokens|Um eine Transaktion auszuführen, muss das Ausführen von ausgestellten Token unterstützt werden.|  
|TrustDriverVersionDoesNotSupportIssuedTokens|Die konfigurierte Trust-Version unterstützt keine ausgestellten Token. Verwenden Sie WSTrustFeb2005 oder höher.|

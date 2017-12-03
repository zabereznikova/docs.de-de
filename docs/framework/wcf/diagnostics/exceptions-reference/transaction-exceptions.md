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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c5896f1f7e15fa7ed86f80bbd7c06ae77faded90
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
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

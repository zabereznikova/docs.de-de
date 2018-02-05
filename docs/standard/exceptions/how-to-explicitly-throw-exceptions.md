---
title: "Gewusst wie: Explizites Auslösen von Ausnahmen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- exceptions, try/catch blocks
- FileNotFoundException class
- try/catch blocks
- exceptions, throwing
- implicitly throwing exceptions
ms.assetid: 72bdd157-caa9-4478-9ee3-cb4500b84528
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 02576db4b9920a367ac3111f2c2c49989ea45149
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-explicitly-throw-exceptions"></a>Explizites Auslösen von Ausnahmen

Sie können mithilfe der `throw`-Anweisung eine Ausnahme explizit auslösen. Mit der `throw`-Anweisung können Sie auch eine abgefangene Ausnahme erneut auslösen. Es ist sinnvoll, einer Ausnahme, die erneut ausgelöst wird, weitere Informationen hinzuzufügen, um das Debuggen zu vereinfachen.

Das folgende Codebeispiel verwendet einen `try`/`catch`-Block, um eine <xref:System.IO.FileNotFoundException> abzufangen. Auf den `try`-Block folgt ein `catch`-Block, der die <xref:System.IO.FileNotFoundException> abfängt und eine Meldung an die Konsole schreibt, wenn die Datendatei nicht gefunden wird. Die nächste Anweisung ist die `throw`-Anweisung, die eine neue <xref:System.IO.FileNotFoundException> auslöst und der Ausnahme Textinformationen hinzufügt.

[!code-csharp[Exception.Throwing#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Exception.Throwing/CS/throw.cs#1)]
[!code-vb[Exception.Throwing#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Exception.Throwing/VB/throw.vb#1)]  

## <a name="see-also"></a>Siehe auch  
[Ausnahmen](index.md)

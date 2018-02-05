---
title: 'Gewusst wie: Erstellen benutzerdefinierter Ausnahmen'
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
- cpp
helpviewer_keywords:
- user-defined exceptions
- exceptions, examples
- exceptions, user-defined
ms.assetid: 25819a5a-f915-4fc8-b924-a76915674e04
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: c55489a4c0b86142fcda99c5962c896b73691cd6
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-create-user-defined-exceptions"></a><span data-ttu-id="a04e5-102">Erstellen benutzerdefinierter Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="a04e5-102">How to create user-defined exceptions</span></span>

<span data-ttu-id="a04e5-103">.NET stellt eine Hierarchie aus Ausnahmeklassen bereit, die letztendlich von der <xref:System.Exception>-Basisklasse abgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="a04e5-103">.NET provides a hierarchy of exception classes ultimately derived from the base class <xref:System.Exception>.</span></span> <span data-ttu-id="a04e5-104">Wenn keine der vordefinierten Ausnahmen Ihre Anforderungen erfüllt, können Sie durch Ableiten von der <xref:System.Exception>-Klasse eigene Ausnahmeklassen erstellen.</span><span class="sxs-lookup"><span data-stu-id="a04e5-104">However, if none of the predefined exceptions meets your needs, you can create your own exception classes by deriving from the <xref:System.Exception> class.</span></span>

<span data-ttu-id="a04e5-105">Beim Erstellen eigener Ausnahmen muss der Klassenname der benutzerdefinierten Ausnahme auf das Wort „Exception“ enden. Implementieren Sie außerdem die drei allgemeinen Konstruktoren, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="a04e5-105">When creating your own exceptions, end the class name of the user-defined exception with the word "Exception," and implement the three common constructors, as shown in the following example.</span></span> <span data-ttu-id="a04e5-106">Das Beispiel definiert eine neue Ausnahmeklasse namens `EmployeeListNotFoundException`.</span><span class="sxs-lookup"><span data-stu-id="a04e5-106">The example defines a new exception class named `EmployeeListNotFoundException`.</span></span> <span data-ttu-id="a04e5-107">Die Klasse wird von <xref:System.Exception> abgeleitet und enthält drei Konstruktoren.</span><span class="sxs-lookup"><span data-stu-id="a04e5-107">The class is derived from <xref:System.Exception> and includes three constructors.</span></span>

[!code-cpp[dg_exceptionDesign#14](../../../samples/snippets/cpp/VS_Snippets_CLR/dg_exceptionDesign/cpp/example2.cpp#14)]
[!code-csharp[dg_exceptionDesign#14](../../../samples/snippets/csharp/VS_Snippets_CLR/dg_exceptionDesign/cs/example2.cs#14)]
[!code-vb[dg_exceptionDesign#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/dg_exceptionDesign/vb/example2.vb#14)]  

> [!NOTE]
> <span data-ttu-id="a04e5-108">In Situationen, in denen Sie Remoting verwenden, müssen Sie sicherstellen, dass die Metadaten für alle benutzerdefinierten Ausnahmen sowohl auf dem Server (Aufgerufener) als auch für den Client (Proxyobjekt oder Aufrufer) verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="a04e5-108">In situations where you are using remoting, you must ensure that the metadata for any user-defined exceptions is available at the server (callee) and to the client (the proxy object or caller).</span></span> <span data-ttu-id="a04e5-109">Weitere Informationen finden Sie unter [Bewährte Methoden für Ausnahmen](best-practices-for-exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="a04e5-109">For more information, see [Best practices for exceptions](best-practices-for-exceptions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a04e5-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a04e5-110">See Also</span></span>  
[<span data-ttu-id="a04e5-111">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="a04e5-111">Exceptions</span></span>](index.md)

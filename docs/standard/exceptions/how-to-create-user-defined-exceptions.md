---
title: 'Gewusst wie: Erstellen benutzerdefinierter Ausnahmen'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- user-defined exceptions
- exceptions, examples
- exceptions, user-defined
ms.assetid: 25819a5a-f915-4fc8-b924-a76915674e04
ms.openlocfilehash: 6de00490a17fff005dd50a7acc5247089c073f68
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "75708874"
---
# <a name="how-to-create-user-defined-exceptions"></a><span data-ttu-id="9f440-102">Erstellen benutzerdefinierter Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="9f440-102">How to create user-defined exceptions</span></span>

<span data-ttu-id="9f440-103">.NET stellt eine Hierarchie aus Ausnahmeklassen bereit, die letztendlich von der <xref:System.Exception>-Basisklasse abgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="9f440-103">.NET provides a hierarchy of exception classes ultimately derived from the base class <xref:System.Exception>.</span></span> <span data-ttu-id="9f440-104">Wenn keine der vordefinierten Ausnahmen Ihre Anforderungen erfüllt, können Sie durch Ableiten von der <xref:System.Exception>-Klasse eigene Ausnahmeklassen erstellen.</span><span class="sxs-lookup"><span data-stu-id="9f440-104">However, if none of the predefined exceptions meets your needs, you can create your own exception classes by deriving from the <xref:System.Exception> class.</span></span>

<span data-ttu-id="9f440-105">Beim Erstellen eigener Ausnahmen muss der Klassenname der benutzerdefinierten Ausnahme auf das Wort „Exception“ enden. Implementieren Sie außerdem die drei allgemeinen Konstruktoren, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="9f440-105">When creating your own exceptions, end the class name of the user-defined exception with the word "Exception", and implement the three common constructors, as shown in the following example.</span></span> <span data-ttu-id="9f440-106">Das Beispiel definiert eine neue Ausnahmeklasse namens `EmployeeListNotFoundException`.</span><span class="sxs-lookup"><span data-stu-id="9f440-106">The example defines a new exception class named `EmployeeListNotFoundException`.</span></span> <span data-ttu-id="9f440-107">Die Klasse wird von <xref:System.Exception> abgeleitet und enthält drei Konstruktoren.</span><span class="sxs-lookup"><span data-stu-id="9f440-107">The class is derived from <xref:System.Exception> and includes three constructors.</span></span>

[!code-cpp[dg_exceptionDesign#14](../../../samples/snippets/cpp/VS_Snippets_CLR/dg_exceptionDesign/cpp/example2.cpp#14)]
[!code-csharp[dg_exceptionDesign#14](../../../samples/snippets/csharp/VS_Snippets_CLR/dg_exceptionDesign/cs/example2.cs#14)]
[!code-vb[dg_exceptionDesign#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/dg_exceptionDesign/vb/example2.vb#14)]  

> [!NOTE]
> <span data-ttu-id="9f440-108">In Situationen, in denen Sie Remoting verwenden, müssen Sie sicherstellen, dass die Metadaten für alle benutzerdefinierten Ausnahmen sowohl auf dem Server (Aufgerufener) als auch für den Client (Proxyobjekt oder Aufrufer) verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="9f440-108">In situations where you are using remoting, you must ensure that the metadata for any user-defined exceptions is available at the server (callee) and to the client (the proxy object or caller).</span></span> <span data-ttu-id="9f440-109">Weitere Informationen finden Sie unter [Bewährte Methoden für Ausnahmen](best-practices-for-exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="9f440-109">For more information, see [Best practices for exceptions](best-practices-for-exceptions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9f440-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9f440-110">See also</span></span>

- [<span data-ttu-id="9f440-111">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="9f440-111">Exceptions</span></span>](index.md)

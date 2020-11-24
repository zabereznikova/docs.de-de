---
title: 'Vorgehensweise: Erstellen benutzerdefinierter Ausnahmen'
description: Erfahren Sie, wie Sie benutzerdefinierte Ausnahmen erstellen. Diese stellen eine Alternative zur Hierarchie von Ausnahmeklassen dar, die von der Exception-Basisklasse in .NET abgeleitet sind.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- user-defined exceptions
- exceptions, examples
- exceptions, user-defined
ms.assetid: 25819a5a-f915-4fc8-b924-a76915674e04
ms.openlocfilehash: b0a8549c9bacf322a0685c7b505185ab1d1101f6
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94828126"
---
# <a name="how-to-create-user-defined-exceptions"></a><span data-ttu-id="0500c-103">Erstellen benutzerdefinierter Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="0500c-103">How to create user-defined exceptions</span></span>

<span data-ttu-id="0500c-104">.NET stellt eine Hierarchie aus Ausnahmeklassen bereit, die letztendlich von der <xref:System.Exception>-Basisklasse abgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="0500c-104">.NET provides a hierarchy of exception classes ultimately derived from the base class <xref:System.Exception>.</span></span> <span data-ttu-id="0500c-105">Wenn keine der vordefinierten Ausnahmen Ihre Anforderungen erfüllt, können Sie durch Ableiten von der <xref:System.Exception>-Klasse eigene Ausnahmeklassen erstellen.</span><span class="sxs-lookup"><span data-stu-id="0500c-105">However, if none of the predefined exceptions meets your needs, you can create your own exception classes by deriving from the <xref:System.Exception> class.</span></span>

<span data-ttu-id="0500c-106">Beim Erstellen eigener Ausnahmen muss der Klassenname der benutzerdefinierten Ausnahme auf das Wort „Exception“ enden. Implementieren Sie außerdem die drei allgemeinen Konstruktoren, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="0500c-106">When creating your own exceptions, end the class name of the user-defined exception with the word "Exception", and implement the three common constructors, as shown in the following example.</span></span> <span data-ttu-id="0500c-107">Das Beispiel definiert eine neue Ausnahmeklasse namens `EmployeeListNotFoundException`.</span><span class="sxs-lookup"><span data-stu-id="0500c-107">The example defines a new exception class named `EmployeeListNotFoundException`.</span></span> <span data-ttu-id="0500c-108">Die Klasse wird von <xref:System.Exception> abgeleitet und enthält drei Konstruktoren.</span><span class="sxs-lookup"><span data-stu-id="0500c-108">The class is derived from <xref:System.Exception> and includes three constructors.</span></span>

[!code-cpp[dg_exceptionDesign#14](../../../samples/snippets/cpp/VS_Snippets_CLR/dg_exceptionDesign/cpp/example2.cpp#14)]
[!code-csharp[dg_exceptionDesign#14](../../../samples/snippets/csharp/VS_Snippets_CLR/dg_exceptionDesign/cs/example2.cs#14)]
[!code-vb[dg_exceptionDesign#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/dg_exceptionDesign/vb/example2.vb#14)]  

> [!NOTE]
> <span data-ttu-id="0500c-109">In Situationen, in denen Sie Remoting verwenden, müssen Sie sicherstellen, dass die Metadaten für alle benutzerdefinierten Ausnahmen sowohl auf dem Server (Aufgerufener) als auch für den Client (Proxyobjekt oder Aufrufer) verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="0500c-109">In situations where you are using remoting, you must ensure that the metadata for any user-defined exceptions is available at the server (callee) and to the client (the proxy object or caller).</span></span> <span data-ttu-id="0500c-110">Weitere Informationen finden Sie unter [Bewährte Methoden für Ausnahmen](best-practices-for-exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="0500c-110">For more information, see [Best practices for exceptions](best-practices-for-exceptions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0500c-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0500c-111">See also</span></span>

- [<span data-ttu-id="0500c-112">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="0500c-112">Exceptions</span></span>](index.md)

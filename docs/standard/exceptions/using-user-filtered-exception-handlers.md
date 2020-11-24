---
title: Verwenden benutzergefilterter Ausnahmehandler
ms.date: 03/30/2017
helpviewer_keywords:
- user-filtered exceptions
- exceptions, user-filtered
ms.assetid: aa80d155-060d-41b4-a636-1ceb424afee8
ms.openlocfilehash: d98412ed651886afc54e15b346a63dc0c549abd0
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94827983"
---
# <a name="using-user-filtered-exception-handlers"></a><span data-ttu-id="8f9db-102">Verwenden benutzergefilterter Ausnahmehandler</span><span class="sxs-lookup"><span data-stu-id="8f9db-102">Using User-Filtered Exception Handlers</span></span>

<span data-ttu-id="8f9db-103">Visual Basic unterstützt benutzergefilterte Ausnahmen.</span><span class="sxs-lookup"><span data-stu-id="8f9db-103">Currently, Visual Basic supports user-filtered exceptions.</span></span> <span data-ttu-id="8f9db-104">Benutzergefilterte Handler fangen und behandeln Ausnahmen gemäß benutzerdefinierten Ausnahmeanforderungen.</span><span class="sxs-lookup"><span data-stu-id="8f9db-104">User-filtered exception handlers catch and handle exceptions based on requirements you define for the exception.</span></span> <span data-ttu-id="8f9db-105">In diesen Handlern wird die **Catch**-Anweisung mit dem Schlüsselwort **When** verwendet.</span><span class="sxs-lookup"><span data-stu-id="8f9db-105">These handlers use the **Catch** statement with the **When** keyword.</span></span>  
  
 <span data-ttu-id="8f9db-106">Dieses Verfahren ist nützlich, wenn ein bestimmtes Ausnahmeobjekt mehreren Fehlern entspricht.</span><span class="sxs-lookup"><span data-stu-id="8f9db-106">This technique is useful when a particular exception object corresponds to multiple errors.</span></span> <span data-ttu-id="8f9db-107">In diesem Fall hat das Objekt in der Regel eine Eigenschaft, die den speziellen Fehlercode enthält, der mit dem Fehler verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="8f9db-107">In this case, the object typically has a property that contains the specific error code associated with the error.</span></span> <span data-ttu-id="8f9db-108">Sie können die Eigenschaft, die den Fehlercode enthält, im Ausdruck dazu verwenden, nur den bestimmten Fehler auszuwählen, den Sie in dieser **Catch**-Klausel behandeln möchten.</span><span class="sxs-lookup"><span data-stu-id="8f9db-108">You can use the error code property in the expression to select only the particular error you want to handle in that **Catch** clause.</span></span>  
  
 <span data-ttu-id="8f9db-109">Im folgenden Visual Basic-Beispiel wird die **Catch/When**-Anweisung veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="8f9db-109">The following Visual Basic example illustrates the **Catch/When** statement.</span></span>  
  
```vb
Try  
    'Try statements.  
    Catch When Err = VBErr_ClassLoadException
    'Catch statements.
End Try  
```  
  
 <span data-ttu-id="8f9db-110">Der Ausdruck der benutzergefilterten Klausel ist in keiner Weise eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="8f9db-110">The expression of the user-filtered clause is not restricted in any way.</span></span> <span data-ttu-id="8f9db-111">Tritt während der Ausführung des benutzergefilterten Ausdrucks eine Ausnahme auf, wird diese Ausnahme verworfen, und der Filterausdruck wird so bewertet, als habe er das Ergebnis „false“ gehabt.</span><span class="sxs-lookup"><span data-stu-id="8f9db-111">If an exception occurs during execution of the user-filtered expression, that exception is discarded and the filter expression is considered to have evaluated to false.</span></span> <span data-ttu-id="8f9db-112">In diesem Fall setzt die Common Language Runtime die Suche nach einem Handler für die aktuelle Ausnahme fort.</span><span class="sxs-lookup"><span data-stu-id="8f9db-112">In this case, the common language runtime continues the search for a handler for the current exception.</span></span>  
  
## <a name="combining-the-specific-exception-and-the-user-filtered-clauses"></a><span data-ttu-id="8f9db-113">Kombinieren der speziellen Ausnahme und der benutzergefilterten Klauseln</span><span class="sxs-lookup"><span data-stu-id="8f9db-113">Combining the Specific Exception and the User-Filtered Clauses</span></span>  
 <span data-ttu-id="8f9db-114">Eine Catch-Anweisung kann sowohl die spezielle Ausnahme als auch die benutzergefilterten Klauseln enthalten.</span><span class="sxs-lookup"><span data-stu-id="8f9db-114">A catch statement can contain both the specific exception and the user-filtered clauses.</span></span> <span data-ttu-id="8f9db-115">Die Runtime prüft zuerst die spezielle Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="8f9db-115">The runtime tests the specific exception first.</span></span> <span data-ttu-id="8f9db-116">Wird die spezielle Ausnahme erfolgreich abgefangen, führt die Runtime den Benutzerfilter aus.</span><span class="sxs-lookup"><span data-stu-id="8f9db-116">If the specific exception succeeds, the runtime executes the user filter.</span></span> <span data-ttu-id="8f9db-117">Der allgemeine Filter kann einen Verweis auf die Variable enthalten, die im Klassenfilter deklariert ist.</span><span class="sxs-lookup"><span data-stu-id="8f9db-117">The generic filter can contain a reference to the variable declared in the class filter.</span></span> <span data-ttu-id="8f9db-118">Die Reihenfolge der beiden Filterklauseln nicht umgekehrt werden.</span><span class="sxs-lookup"><span data-stu-id="8f9db-118">Note that the order of the two filter clauses cannot be reversed.</span></span>  
  
 <span data-ttu-id="8f9db-119">Im folgenden Visual Basic-Beispiel werden die spezielle Ausnahme `ClassLoadException` in der **Catch**-Anweisung sowie die benutzergefilterte Klausel mit dem Schlüsselwort **When** veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="8f9db-119">The following Visual Basic example shows the specific exception `ClassLoadException` in the **Catch** statement as well as the user-filtered clause using the **When** keyword.</span></span>  
  
```vb
Try  
    'Try statements.
    Catch cle As ClassLoadException When cle.IsRecoverable()  
    'Catch statements.
End Try  
```  

## <a name="see-also"></a><span data-ttu-id="8f9db-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8f9db-120">See also</span></span>

- [<span data-ttu-id="8f9db-121">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="8f9db-121">Exceptions</span></span>](index.md)

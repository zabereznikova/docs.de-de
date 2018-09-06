---
title: 'Gewusst wie: Entfernen aller Verweise einer Objektvariablen auf Instanzen (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- Nothing keyword [Visual Basic], variable assignment
- object variables [Visual Basic], null reference
ms.assetid: e6d30578-bdae-4142-a3ac-a10697bf696a
ms.openlocfilehash: 8f85ba0adea522851e45b20ef5024491874c9a29
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "44042516"
---
# <a name="how-to-make-an-object-variable-not-refer-to-any-instance-visual-basic"></a><span data-ttu-id="bd7ef-102">Gewusst wie: Entfernen aller Verweise einer Objektvariablen auf Instanzen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bd7ef-102">How to: Make an Object Variable Not Refer to Any Instance (Visual Basic)</span></span>
<span data-ttu-id="bd7ef-103">Sie können die Zuordnung einer Objektvariablen von jeder Objektinstanz aufheben, durch Festlegung auf [nichts](../../../../visual-basic/language-reference/nothing.md).</span><span class="sxs-lookup"><span data-stu-id="bd7ef-103">You can disassociate an object variable from any object instance by setting it to [Nothing](../../../../visual-basic/language-reference/nothing.md).</span></span>  
  
### <a name="to-disassociate-an-object-variable-from-any-object-instance"></a><span data-ttu-id="bd7ef-104">Aufheben der Zuordnung eine Objektvariablen von jeder Objektinstanz</span><span class="sxs-lookup"><span data-stu-id="bd7ef-104">To disassociate an object variable from any object instance</span></span>  
  
-   <span data-ttu-id="bd7ef-105">Legen Sie die Variable auf `Nothing` in einer zuweisungsanweisung.</span><span class="sxs-lookup"><span data-stu-id="bd7ef-105">Set the variable to `Nothing` in an assignment statement.</span></span>  
  
    ```  
    ' Assume account is a defined class  
    Dim currentAccount As account  
    currentAccount = Nothing  
    ```  
  
## <a name="robust-programming"></a><span data-ttu-id="bd7ef-106">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="bd7ef-106">Robust Programming</span></span>  
 <span data-ttu-id="bd7ef-107">Wenn Ihr Code versucht, den Zugriff auf einen Member einer Objektvariablen, die festgelegt wurde, `Nothing`, <xref:System.NullReferenceException> auftritt.</span><span class="sxs-lookup"><span data-stu-id="bd7ef-107">If your code tries to access a member of an object variable that has been set to `Nothing`, a <xref:System.NullReferenceException> occurs.</span></span> <span data-ttu-id="bd7ef-108">Wenn Sie eine Objektvariablen auf `Nothing` in vielen Fällen oder wenn es möglich, die die Variable ist nicht initialisiert ist, ist es eine gute Idee, schließen Sie Memberzugriff in einem `Try...Catch...Finally` Block.</span><span class="sxs-lookup"><span data-stu-id="bd7ef-108">If you set an object variable to `Nothing` frequently, or if it is possible the variable is not initialized, it is a good idea to enclose member accesses in a `Try...Catch...Finally` block.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="bd7ef-109">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="bd7ef-109">.NET Framework Security</span></span>  
 <span data-ttu-id="bd7ef-110">Wenn Sie eine Objektvariablen für Objekte, die vertrauliche oder sensible Daten enthalten verwenden, können Sie die Variable festlegen, um `Nothing` Wenn Sie nicht aktiv zuständig sind mit einem dieser Objekte.</span><span class="sxs-lookup"><span data-stu-id="bd7ef-110">If you use an object variable for objects that contain confidential or sensitive data, you can set the variable to `Nothing` when you are not actively dealing with one of those objects.</span></span> <span data-ttu-id="bd7ef-111">Dies reduziert die Wahrscheinlichkeit, dass bösartiger Code, um Zugriff auf die Daten.</span><span class="sxs-lookup"><span data-stu-id="bd7ef-111">This reduces the chance of malicious code gaining access to the data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd7ef-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bd7ef-112">See Also</span></span>  
 <xref:System.NullReferenceException>  
 [<span data-ttu-id="bd7ef-113">Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="bd7ef-113">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [<span data-ttu-id="bd7ef-114">Zuweisen von Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="bd7ef-114">Object Variable Assignment</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)  
 [<span data-ttu-id="bd7ef-115">Nothing</span><span class="sxs-lookup"><span data-stu-id="bd7ef-115">Nothing</span></span>](../../../../visual-basic/language-reference/nothing.md)  
 [<span data-ttu-id="bd7ef-116">Try...Catch...Finally-Anweisung</span><span class="sxs-lookup"><span data-stu-id="bd7ef-116">Try...Catch...Finally Statement</span></span>](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [<span data-ttu-id="bd7ef-117">Problembehandlung bei Ausnahmen: System.NullReferenceException</span><span class="sxs-lookup"><span data-stu-id="bd7ef-117">Troubleshooting Exceptions: System.NullReferenceException</span></span>](https://msdn.microsoft.com/library/4822b0b4-8105-43fb-887a-3cc51ff02899)

---
title: 'Vorgehensweise: Einer Objektvariablen verweist nicht auf eine beliebige Instanz (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- Nothing keyword [Visual Basic], variable assignment
- object variables [Visual Basic], null reference
ms.assetid: e6d30578-bdae-4142-a3ac-a10697bf696a
ms.openlocfilehash: 373d4ae84c44b212ad02b0b4266af75921e40423
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58818688"
---
# <a name="how-to-make-an-object-variable-not-refer-to-any-instance-visual-basic"></a><span data-ttu-id="04d78-102">Vorgehensweise: Einer Objektvariablen verweist nicht auf eine beliebige Instanz (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="04d78-102">How to: Make an Object Variable Not Refer to Any Instance (Visual Basic)</span></span>
<span data-ttu-id="04d78-103">Sie können die Zuordnung einer Objektvariablen von jeder Objektinstanz aufheben, durch Festlegung auf [nichts](../../../../visual-basic/language-reference/nothing.md).</span><span class="sxs-lookup"><span data-stu-id="04d78-103">You can disassociate an object variable from any object instance by setting it to [Nothing](../../../../visual-basic/language-reference/nothing.md).</span></span>  
  
### <a name="to-disassociate-an-object-variable-from-any-object-instance"></a><span data-ttu-id="04d78-104">Aufheben der Zuordnung eine Objektvariablen von jeder Objektinstanz</span><span class="sxs-lookup"><span data-stu-id="04d78-104">To disassociate an object variable from any object instance</span></span>  
  
-   <span data-ttu-id="04d78-105">Legen Sie die Variable auf `Nothing` in einer zuweisungsanweisung.</span><span class="sxs-lookup"><span data-stu-id="04d78-105">Set the variable to `Nothing` in an assignment statement.</span></span>  
  
    ```  
    ' Assume account is a defined class  
    Dim currentAccount As account  
    currentAccount = Nothing  
    ```  
  
## <a name="robust-programming"></a><span data-ttu-id="04d78-106">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="04d78-106">Robust Programming</span></span>  
 <span data-ttu-id="04d78-107">Wenn Ihr Code versucht, den Zugriff auf einen Member einer Objektvariablen, die festgelegt wurde, `Nothing`, <xref:System.NullReferenceException> auftritt.</span><span class="sxs-lookup"><span data-stu-id="04d78-107">If your code tries to access a member of an object variable that has been set to `Nothing`, a <xref:System.NullReferenceException> occurs.</span></span> <span data-ttu-id="04d78-108">Wenn Sie eine Objektvariablen auf `Nothing` in vielen Fällen oder wenn es möglich, die die Variable ist nicht initialisiert ist, ist es eine gute Idee, schließen Sie Memberzugriff in einem `Try...Catch...Finally` Block.</span><span class="sxs-lookup"><span data-stu-id="04d78-108">If you set an object variable to `Nothing` frequently, or if it is possible the variable is not initialized, it is a good idea to enclose member accesses in a `Try...Catch...Finally` block.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="04d78-109">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="04d78-109">.NET Framework Security</span></span>  
 <span data-ttu-id="04d78-110">Wenn Sie eine Objektvariablen für Objekte, die vertrauliche oder sensible Daten enthalten verwenden, können Sie die Variable festlegen, um `Nothing` Wenn Sie nicht aktiv zuständig sind mit einem dieser Objekte.</span><span class="sxs-lookup"><span data-stu-id="04d78-110">If you use an object variable for objects that contain confidential or sensitive data, you can set the variable to `Nothing` when you are not actively dealing with one of those objects.</span></span> <span data-ttu-id="04d78-111">Dies reduziert die Wahrscheinlichkeit, dass bösartiger Code, um Zugriff auf die Daten.</span><span class="sxs-lookup"><span data-stu-id="04d78-111">This reduces the chance of malicious code gaining access to the data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04d78-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="04d78-112">See also</span></span>

- <xref:System.NullReferenceException>
- [<span data-ttu-id="04d78-113">Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="04d78-113">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="04d78-114">Zuweisen von Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="04d78-114">Object Variable Assignment</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [<span data-ttu-id="04d78-115">Nothing</span><span class="sxs-lookup"><span data-stu-id="04d78-115">Nothing</span></span>](../../../../visual-basic/language-reference/nothing.md)
- [<span data-ttu-id="04d78-116">Try...Catch...Finally-Anweisung</span><span class="sxs-lookup"><span data-stu-id="04d78-116">Try...Catch...Finally Statement</span></span>](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)

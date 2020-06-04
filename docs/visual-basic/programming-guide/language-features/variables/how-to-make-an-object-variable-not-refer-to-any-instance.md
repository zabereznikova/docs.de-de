---
title: 'Vorgehensweise: Entfernen aller Verweise einer Objektvariablen auf Instanzen'
ms.date: 07/20/2015
helpviewer_keywords:
- Nothing keyword [Visual Basic], variable assignment
- object variables [Visual Basic], null reference
ms.assetid: e6d30578-bdae-4142-a3ac-a10697bf696a
ms.openlocfilehash: cce2e59cb76652937868a731ad308872d1aba2f3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410450"
---
# <a name="how-to-make-an-object-variable-not-refer-to-any-instance-visual-basic"></a><span data-ttu-id="061be-102">Gewusst wie: Entfernen aller Verweise einer Objektvariablen auf Instanzen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="061be-102">How to: Make an Object Variable Not Refer to Any Instance (Visual Basic)</span></span>
<span data-ttu-id="061be-103">Sie können eine Objekt Variable von einer beliebigen Objektinstanz trennen, indem Sie Sie auf " [Nothing](../../../language-reference/nothing.md)" festlegen.</span><span class="sxs-lookup"><span data-stu-id="061be-103">You can disassociate an object variable from any object instance by setting it to [Nothing](../../../language-reference/nothing.md).</span></span>  
  
### <a name="to-disassociate-an-object-variable-from-any-object-instance"></a><span data-ttu-id="061be-104">So trennen Sie eine Objekt Variable zu einer Objektinstanz</span><span class="sxs-lookup"><span data-stu-id="061be-104">To disassociate an object variable from any object instance</span></span>  
  
- <span data-ttu-id="061be-105">Legen Sie die Variable `Nothing` in einer Zuweisungsanweisung auf fest.</span><span class="sxs-lookup"><span data-stu-id="061be-105">Set the variable to `Nothing` in an assignment statement.</span></span>  
  
    ```vb  
    ' Assume account is a defined class  
    Dim currentAccount As account  
    currentAccount = Nothing  
    ```  
  
## <a name="robust-programming"></a><span data-ttu-id="061be-106">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="061be-106">Robust Programming</span></span>  
 <span data-ttu-id="061be-107">Wenn Ihr Code versucht, auf einen Member einer Objektvariablen zuzugreifen, die auf festgelegt wurde `Nothing` , <xref:System.NullReferenceException> tritt ein auf.</span><span class="sxs-lookup"><span data-stu-id="061be-107">If your code tries to access a member of an object variable that has been set to `Nothing`, a <xref:System.NullReferenceException> occurs.</span></span> <span data-ttu-id="061be-108">Wenn Sie eine Objekt Variable häufig auf festlegen `Nothing` , oder wenn es möglich ist, die Variable nicht zu initialisieren, empfiehlt es sich, die Member-Zugriffe in einem- `Try...Catch...Finally` Block zu schließen.</span><span class="sxs-lookup"><span data-stu-id="061be-108">If you set an object variable to `Nothing` frequently, or if it is possible the variable is not initialized, it is a good idea to enclose member accesses in a `Try...Catch...Finally` block.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="061be-109">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="061be-109">.NET Framework Security</span></span>  
 <span data-ttu-id="061be-110">Wenn Sie eine Objekt Variable für Objekte verwenden, die vertrauliche oder sensible Daten enthalten, können Sie die Variable auf festlegen, `Nothing` Wenn Sie nicht aktiv mit einem dieser Objekte arbeiten.</span><span class="sxs-lookup"><span data-stu-id="061be-110">If you use an object variable for objects that contain confidential or sensitive data, you can set the variable to `Nothing` when you are not actively dealing with one of those objects.</span></span> <span data-ttu-id="061be-111">Dadurch wird die Wahrscheinlichkeit verringert, dass bösartiger Code Zugriff auf die Daten erhält.</span><span class="sxs-lookup"><span data-stu-id="061be-111">This reduces the chance of malicious code gaining access to the data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="061be-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="061be-112">See also</span></span>

- <xref:System.NullReferenceException>
- [<span data-ttu-id="061be-113">Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="061be-113">Object Variables</span></span>](object-variables.md)
- [<span data-ttu-id="061be-114">Zuweisung von Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="061be-114">Object Variable Assignment</span></span>](object-variable-assignment.md)
- [<span data-ttu-id="061be-115">Schweigen</span><span class="sxs-lookup"><span data-stu-id="061be-115">Nothing</span></span>](../../../language-reference/nothing.md)
- [<span data-ttu-id="061be-116">Try...Catch...Finally-Anweisung</span><span class="sxs-lookup"><span data-stu-id="061be-116">Try...Catch...Finally Statement</span></span>](../../../language-reference/statements/try-catch-finally-statement.md)

---
title: Der Ausdruck ruft rekursiv die enthaltende <propertyname>-Eigenschaft auf.
ms.date: 07/20/2015
f1_keywords:
- vbc42026
- BC42026
helpviewer_keywords:
- BC42026
ms.assetid: 4fde9db6-3bf3-48dc-8e05-981bf08969da
ms.openlocfilehash: c05a7d9b021192d53a30e49f52abc08d9b153156
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874257"
---
# <a name="expression-recursively-calls-the-containing-property-propertyname"></a><span data-ttu-id="49bb2-102">Der Ausdruck ruft rekursiv die enthaltende \<propertyname>-Eigenschaft auf.</span><span class="sxs-lookup"><span data-stu-id="49bb2-102">Expression recursively calls the containing property '\<propertyname>'</span></span>

<span data-ttu-id="49bb2-103">Eine-Anweisung in der `Set` Prozedur einer Eigenschafts Definition speichert einen Wert in den Namen der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="49bb2-103">A statement in the `Set` procedure of a property definition stores a value into the name of the property.</span></span>  
  
 <span data-ttu-id="49bb2-104">Die empfohlene Vorgehensweise, um den Wert einer Eigenschaft zu speichern, besteht darin, eine `Private` Variable im Container der Eigenschaft zu definieren und Sie in den `Get` `Set` Prozeduren und zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="49bb2-104">The recommended approach to holding the value of a property is to define a `Private` variable in the property's container and use it in both the `Get` and `Set` procedures.</span></span> <span data-ttu-id="49bb2-105">`Set`In der Prozedur sollte dann der eingehende Wert in dieser Variablen gespeichert werden `Private` .</span><span class="sxs-lookup"><span data-stu-id="49bb2-105">The `Set` procedure should then store the incoming value in this `Private` variable.</span></span>  
  
 <span data-ttu-id="49bb2-106">Die `Get` Prozedur verhält sich wie eine `Function` Prozedur, sodass Sie dem Eigenschaftsnamen einen Wert zuweisen und die Steuerung zurückgeben kann, indem Sie die- `End Get` Anweisung trifft.</span><span class="sxs-lookup"><span data-stu-id="49bb2-106">The `Get` procedure behaves like a `Function` procedure, so it can assign a value to the property name and return control by encountering the `End Get` statement.</span></span> <span data-ttu-id="49bb2-107">Die empfohlene Vorgehensweise besteht jedoch darin, die `Private` Variable als Wert in eine Return- [Anweisung](../statements/return-statement.md)aufzunehmen.</span><span class="sxs-lookup"><span data-stu-id="49bb2-107">The recommended approach, however, is to include the `Private` variable as the value in a [Return Statement](../statements/return-statement.md).</span></span>  
  
 <span data-ttu-id="49bb2-108">Die `Set` Prozedur verhält sich wie eine `Sub` Prozedur, die keinen Wert zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="49bb2-108">The `Set` procedure behaves like a `Sub` procedure, which does not return a value.</span></span> <span data-ttu-id="49bb2-109">Daher hat der Name der Prozedur oder Eigenschaft in einer Prozedur keine besondere Bedeutung `Set` , und Sie können keinen Wert in der Prozedur speichern.</span><span class="sxs-lookup"><span data-stu-id="49bb2-109">Therefore, the procedure or property name has no special meaning within a `Set` procedure, and you cannot store a value into it.</span></span>  
  
 <span data-ttu-id="49bb2-110">Im folgenden Beispiel wird die Vorgehensweise veranschaulicht, die diesen Fehler verursachen kann, gefolgt von der empfohlenen Vorgehensweise.</span><span class="sxs-lookup"><span data-stu-id="49bb2-110">The following example illustrates the approach that can cause this error, followed by the recommended approach.</span></span>  
  
```vb  
Public Class illustrateProperties  
' The code in the following property causes this error.  
    Public Property badProp() As Char  
        Get  
            Dim charValue As Char  
            ' Insert code to update charValue.  
            badProp = charValue  
        End Get  
        Set(ByVal Value As Char)  
            ' The following statement causes this error.  
            badProp = Value  
            ' The value stored in the local variable badProp  
            ' is not used by the Get procedure in this property.  
        End Set  
    End Property  
' The following code uses the recommended approach.  
    Private propValue As Char  
    Public Property goodProp() As Char  
        Get  
            ' Insert code to update propValue.  
            Return propValue  
        End Get  
        Set(ByVal Value As Char)  
            propValue = Value  
        End Set  
    End Property  
End Class  
```  
  
 <span data-ttu-id="49bb2-111">Standardmäßig ist diese Meldung eine Warnung.</span><span class="sxs-lookup"><span data-stu-id="49bb2-111">By default, this message is a warning.</span></span> <span data-ttu-id="49bb2-112">Weitere Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Konfigurieren von Warnungen in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="49bb2-112">For more information about hiding warnings or treating warnings as errors, please see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="49bb2-113">**Fehler-ID:** BC42026</span><span class="sxs-lookup"><span data-stu-id="49bb2-113">**Error ID:** BC42026</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="49bb2-114">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="49bb2-114">To correct this error</span></span>  
  
- <span data-ttu-id="49bb2-115">Schreiben Sie die Eigenschafts Definition so um, dass die empfohlene Vorgehensweise verwendet wird, wie im vorherigen Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="49bb2-115">Rewrite the property definition to use the recommended approach as illustrated in the preceding example.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49bb2-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="49bb2-116">See also</span></span>

- [<span data-ttu-id="49bb2-117">Eigenschaftenprozeduren</span><span class="sxs-lookup"><span data-stu-id="49bb2-117">Property Procedures</span></span>](../../programming-guide/language-features/procedures/property-procedures.md)
- [<span data-ttu-id="49bb2-118">Property Statement</span><span class="sxs-lookup"><span data-stu-id="49bb2-118">Property Statement</span></span>](../statements/property-statement.md)
- [<span data-ttu-id="49bb2-119">Set-Anweisung</span><span class="sxs-lookup"><span data-stu-id="49bb2-119">Set Statement</span></span>](../statements/set-statement.md)

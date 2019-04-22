---
title: Der Ausdruck ruft rekursiv die enthaltende <propertyname>-Eigenschaft auf.
ms.date: 07/20/2015
f1_keywords:
- vbc42026
- BC42026
helpviewer_keywords:
- BC42026
ms.assetid: 4fde9db6-3bf3-48dc-8e05-981bf08969da
ms.openlocfilehash: a758d05cca5ca71943b0ef08184aef5b2c457739
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58836843"
---
# <a name="expression-recursively-calls-the-containing-property-propertyname"></a><span data-ttu-id="8fe1b-102">Der Ausdruck ruft rekursiv die enthaltende Eigenschaft '\<Propertyname >'</span><span class="sxs-lookup"><span data-stu-id="8fe1b-102">Expression recursively calls the containing property '\<propertyname>'</span></span>
<span data-ttu-id="8fe1b-103">Eine Anweisung in der `Set` Definition einer Prozedur speichert einen Wert in den Namen der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="8fe1b-103">A statement in the `Set` procedure of a property definition stores a value into the name of the property.</span></span>  
  
 <span data-ttu-id="8fe1b-104">Der empfohlene Ansatz zum Speichern des Werts einer Eigenschaft wird zum definieren eine `Private` -Variable im Container der Eigenschaft und verwenden in beiden die `Get` und `Set` Verfahren.</span><span class="sxs-lookup"><span data-stu-id="8fe1b-104">The recommended approach to holding the value of a property is to define a `Private` variable in the property's container and use it in both the `Get` and `Set` procedures.</span></span> <span data-ttu-id="8fe1b-105">Die `Set` Prozedur muss dann den eingehenden Wert in dieser speichern `Private` Variable.</span><span class="sxs-lookup"><span data-stu-id="8fe1b-105">The `Set` procedure should then store the incoming value in this `Private` variable.</span></span>  
  
 <span data-ttu-id="8fe1b-106">Die `Get` Prozedur verhält sich wie ein `Function` Prozedur, damit Namen der Eigenschaft einen Wert zuzuweisen und die Steuerung, durch die auftreten zurück können die `End Get` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="8fe1b-106">The `Get` procedure behaves like a `Function` procedure, so it can assign a value to the property name and return control by encountering the `End Get` statement.</span></span> <span data-ttu-id="8fe1b-107">Allerdings wird empfohlen, sollen die `Private` -Variable als den Wert in eine [Return-Anweisung](../../../visual-basic/language-reference/statements/return-statement.md).</span><span class="sxs-lookup"><span data-stu-id="8fe1b-107">The recommended approach, however, is to include the `Private` variable as the value in a [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md).</span></span>  
  
 <span data-ttu-id="8fe1b-108">Die `Set` Prozedur verhält sich wie ein `Sub` -Prozedur, die keinen Wert zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="8fe1b-108">The `Set` procedure behaves like a `Sub` procedure, which does not return a value.</span></span> <span data-ttu-id="8fe1b-109">Aus diesem Grund hat der Prozedur oder Eigenschaft Name keine besondere Bedeutung innerhalb einer `Set` Prozedur, und Sie können keinen Wert darin speichern.</span><span class="sxs-lookup"><span data-stu-id="8fe1b-109">Therefore, the procedure or property name has no special meaning within a `Set` procedure, and you cannot store a value into it.</span></span>  
  
 <span data-ttu-id="8fe1b-110">Das folgende Beispiel veranschaulicht den Ansatz, der diesen Fehler, gefolgt von der empfohlene Ansatz verursachen kann.</span><span class="sxs-lookup"><span data-stu-id="8fe1b-110">The following example illustrates the approach that can cause this error, followed by the recommended approach.</span></span>  
  
```  
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
  
 <span data-ttu-id="8fe1b-111">Standardmäßig ist diese Meldung eine Warnung.</span><span class="sxs-lookup"><span data-stu-id="8fe1b-111">By default, this message is a warning.</span></span> <span data-ttu-id="8fe1b-112">Weitere Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="8fe1b-112">For more information about hiding warnings or treating warnings as errors, please see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="8fe1b-113">**Fehler-ID:** BC42026</span><span class="sxs-lookup"><span data-stu-id="8fe1b-113">**Error ID:** BC42026</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="8fe1b-114">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="8fe1b-114">To correct this error</span></span>  
  
-   <span data-ttu-id="8fe1b-115">Schreiben Sie die Eigenschaftsdefinition, um die empfohlene Vorgehensweise verwenden, wie im vorherigen Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="8fe1b-115">Rewrite the property definition to use the recommended approach as illustrated in the preceding example.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fe1b-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8fe1b-116">See also</span></span>

- [<span data-ttu-id="8fe1b-117">Eigenschaftenprozeduren</span><span class="sxs-lookup"><span data-stu-id="8fe1b-117">Property Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)
- [<span data-ttu-id="8fe1b-118">Property-Anweisung</span><span class="sxs-lookup"><span data-stu-id="8fe1b-118">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="8fe1b-119">Set-Anweisung</span><span class="sxs-lookup"><span data-stu-id="8fe1b-119">Set Statement</span></span>](../../../visual-basic/language-reference/statements/set-statement.md)

---
title: Der Ausdruck ruft rekursiv die enthaltende <propertyname>-Eigenschaft auf.
ms.date: 07/20/2015
f1_keywords:
- vbc42026
- BC42026
helpviewer_keywords:
- BC42026
ms.assetid: 4fde9db6-3bf3-48dc-8e05-981bf08969da
ms.openlocfilehash: 42177f22e632e4a05b1f0b4d934f3e56ab9ff0f2
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698570"
---
# <a name="expression-recursively-calls-the-containing-property-propertyname"></a><span data-ttu-id="84f70-102">Der Ausdruck ruft rekursiv die enthaltende Eigenschaft ' \<propertyname > ' auf.</span><span class="sxs-lookup"><span data-stu-id="84f70-102">Expression recursively calls the containing property '\<propertyname>'</span></span>
<span data-ttu-id="84f70-103">Eine-Anweisung in der `Set`-Prozedur einer Eigenschafts Definition speichert einen Wert in den Namen der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="84f70-103">A statement in the `Set` procedure of a property definition stores a value into the name of the property.</span></span>  
  
 <span data-ttu-id="84f70-104">Die empfohlene Vorgehensweise, um den Wert einer Eigenschaft zu speichern, besteht darin, eine `Private`-Variable im Container der Eigenschaft zu definieren und Sie in den Prozeduren `Get` und `Set` zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="84f70-104">The recommended approach to holding the value of a property is to define a `Private` variable in the property's container and use it in both the `Get` and `Set` procedures.</span></span> <span data-ttu-id="84f70-105">In der `Set`-Prozedur sollte der eingehende Wert in dieser `Private`-Variablen gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="84f70-105">The `Set` procedure should then store the incoming value in this `Private` variable.</span></span>  
  
 <span data-ttu-id="84f70-106">Die Prozedur `Get` verhält sich wie eine `Function`-Prozedur, sodass Sie dem Eigenschaftsnamen einen Wert zuweisen und die Steuerung zurückgeben kann, indem Sie die `End Get`-Anweisung trifft.</span><span class="sxs-lookup"><span data-stu-id="84f70-106">The `Get` procedure behaves like a `Function` procedure, so it can assign a value to the property name and return control by encountering the `End Get` statement.</span></span> <span data-ttu-id="84f70-107">Die empfohlene Vorgehensweise besteht jedoch darin, die `Private`-Variable als Wert in eine [Return-Anweisung](../../../visual-basic/language-reference/statements/return-statement.md)einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="84f70-107">The recommended approach, however, is to include the `Private` variable as the value in a [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md).</span></span>  
  
 <span data-ttu-id="84f70-108">Die Prozedur `Set` verhält sich wie eine `Sub`-Prozedur, die keinen Wert zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="84f70-108">The `Set` procedure behaves like a `Sub` procedure, which does not return a value.</span></span> <span data-ttu-id="84f70-109">Daher hat der Name der Prozedur oder Eigenschaft in einer `Set`-Prozedur keine besondere Bedeutung, und Sie können keinen Wert in der Prozedur speichern.</span><span class="sxs-lookup"><span data-stu-id="84f70-109">Therefore, the procedure or property name has no special meaning within a `Set` procedure, and you cannot store a value into it.</span></span>  
  
 <span data-ttu-id="84f70-110">Im folgenden Beispiel wird die Vorgehensweise veranschaulicht, die diesen Fehler verursachen kann, gefolgt von der empfohlenen Vorgehensweise.</span><span class="sxs-lookup"><span data-stu-id="84f70-110">The following example illustrates the approach that can cause this error, followed by the recommended approach.</span></span>  
  
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
  
 <span data-ttu-id="84f70-111">Standardmäßig ist diese Meldung eine Warnung.</span><span class="sxs-lookup"><span data-stu-id="84f70-111">By default, this message is a warning.</span></span> <span data-ttu-id="84f70-112">Weitere Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="84f70-112">For more information about hiding warnings or treating warnings as errors, please see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="84f70-113">**Fehler-ID:** BC42026</span><span class="sxs-lookup"><span data-stu-id="84f70-113">**Error ID:** BC42026</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="84f70-114">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="84f70-114">To correct this error</span></span>  
  
- <span data-ttu-id="84f70-115">Schreiben Sie die Eigenschafts Definition so um, dass die empfohlene Vorgehensweise verwendet wird, wie im vorherigen Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="84f70-115">Rewrite the property definition to use the recommended approach as illustrated in the preceding example.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84f70-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="84f70-116">See also</span></span>

- [<span data-ttu-id="84f70-117">Eigenschaftenprozeduren</span><span class="sxs-lookup"><span data-stu-id="84f70-117">Property Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)
- [<span data-ttu-id="84f70-118">Property-Anweisung</span><span class="sxs-lookup"><span data-stu-id="84f70-118">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="84f70-119">Set-Anweisung</span><span class="sxs-lookup"><span data-stu-id="84f70-119">Set Statement</span></span>](../../../visual-basic/language-reference/statements/set-statement.md)

---
title: Der Ausdruck ruft rekursiv die enthaltende Eigenschaft &quot;&lt;Propertyname&gt;&quot; | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc42026
- BC42026
dev_langs:
- VB
helpviewer_keywords:
- BC42026
ms.assetid: 4fde9db6-3bf3-48dc-8e05-981bf08969da
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: c7168ab2a2ec5eb0c0d423120b67c10b117c14b2
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="expression-recursively-calls-the-containing-property-39ltpropertynamegt39"></a><span data-ttu-id="1f5be-102">Der Ausdruck ruft rekursiv die enthaltende Eigenschaft '&lt;Propertyname&gt;'</span><span class="sxs-lookup"><span data-stu-id="1f5be-102">Expression recursively calls the containing property &#39;&lt;propertyname&gt;&#39;</span></span>
<span data-ttu-id="1f5be-103">Eine Anweisung in der `Set` -Prozedur einer Eigenschaftendefinition speichert einen Wert in den Namen der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="1f5be-103">A statement in the `Set` procedure of a property definition stores a value into the name of the property.</span></span>  
  
 <span data-ttu-id="1f5be-104">Die empfohlene Vorgehensweise zum Speichern des Werts einer Eigenschaft definiert ist ein `Private` -Variable im Container der Eigenschaft und deren Verwendung in beide die `Get` und `Set` Verfahren.</span><span class="sxs-lookup"><span data-stu-id="1f5be-104">The recommended approach to holding the value of a property is to define a `Private` variable in the property's container and use it in both the `Get` and `Set` procedures.</span></span> <span data-ttu-id="1f5be-105">Die `Set` -Prozedur muss dann den eingehenden Wert in dieser speichern `Private` Variable.</span><span class="sxs-lookup"><span data-stu-id="1f5be-105">The `Set` procedure should then store the incoming value in this `Private` variable.</span></span>  
  
 <span data-ttu-id="1f5be-106">Die `Get` Prozedur verhält sich wie eine `Function` Prozedur, den Eigenschaftennamen einen Wert zuzuweisen und Steuerung von auftreten zurück der `End Get` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="1f5be-106">The `Get` procedure behaves like a `Function` procedure, so it can assign a value to the property name and return control by encountering the `End Get` statement.</span></span> <span data-ttu-id="1f5be-107">Jedoch wird empfohlen, enthalten die `Private` -Variable als Wert in einer [Return-Anweisung](../../../visual-basic/language-reference/statements/return-statement.md).</span><span class="sxs-lookup"><span data-stu-id="1f5be-107">The recommended approach, however, is to include the `Private` variable as the value in a [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md).</span></span>  
  
 <span data-ttu-id="1f5be-108">Die `Set` Prozedur verhält sich wie eine `Sub` Prozedur, die keinen Wert zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="1f5be-108">The `Set` procedure behaves like a `Sub` procedure, which does not return a value.</span></span> <span data-ttu-id="1f5be-109">Name der Prozedur oder Eigenschaft hat daher keine besondere Bedeutung innerhalb einer `Set` Prozedur, und Sie können keinen Wert darin speichern.</span><span class="sxs-lookup"><span data-stu-id="1f5be-109">Therefore, the procedure or property name has no special meaning within a `Set` procedure, and you cannot store a value into it.</span></span>  
  
 <span data-ttu-id="1f5be-110">Das folgende Beispiel veranschaulicht die Vorgehensweise, die diesen Fehler, gefolgt von der empfohlene Ansatz.</span><span class="sxs-lookup"><span data-stu-id="1f5be-110">The following example illustrates the approach that can cause this error, followed by the recommended approach.</span></span>  
  
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
  
 <span data-ttu-id="1f5be-111">Standardmäßig ist diese Meldung eine Warnung.</span><span class="sxs-lookup"><span data-stu-id="1f5be-111">By default, this message is a warning.</span></span> <span data-ttu-id="1f5be-112">Weitere Informationen zum Ausblenden von Warnungen oder Warnungen als Fehler behandeln, finden Sie unter [Konfigurieren von Warnungen in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="1f5be-112">For more information about hiding warnings or treating warnings as errors, please see [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="1f5be-113">**Fehler-ID:** BC42026</span><span class="sxs-lookup"><span data-stu-id="1f5be-113">**Error ID:** BC42026</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="1f5be-114">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="1f5be-114">To correct this error</span></span>  
  
-   <span data-ttu-id="1f5be-115">Schreiben Sie die Eigenschaftsdefinition, um die empfohlene Vorgehensweise verwenden, wie im vorherigen Beispiel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="1f5be-115">Rewrite the property definition to use the recommended approach as illustrated in the preceding example.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f5be-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1f5be-116">See Also</span></span>  
 <span data-ttu-id="1f5be-117">[Property-Prozeduren](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="1f5be-117">[Property Procedures](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md) </span></span>  
<span data-ttu-id="1f5be-118"> [Property-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md) </span><span class="sxs-lookup"><span data-stu-id="1f5be-118"> [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md) </span></span>  
<span data-ttu-id="1f5be-119"> [Set-Anweisung](../../../visual-basic/language-reference/statements/set-statement.md)</span><span class="sxs-lookup"><span data-stu-id="1f5be-119"> [Set Statement](../../../visual-basic/language-reference/statements/set-statement.md)</span></span>

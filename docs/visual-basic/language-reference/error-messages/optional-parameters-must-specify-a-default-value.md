---
title: Optionale Parameter müssen einen Standardwert bestimmen.
ms.date: 07/20/2015
f1_keywords:
- vbc30812
- bc30812
helpviewer_keywords:
- BC30812
ms.assetid: 5091a250-be66-413b-98a3-2a9974c4d600
ms.openlocfilehash: dbbcc748a65942e3a89785b267e9231f4a4a01a8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54686178"
---
# <a name="optional-parameters-must-specify-a-default-value"></a><span data-ttu-id="93c27-102">Optionale Parameter müssen einen Standardwert bestimmen.</span><span class="sxs-lookup"><span data-stu-id="93c27-102">Optional parameters must specify a default value</span></span>
<span data-ttu-id="93c27-103">Optionale Parameter müssen Standardwerte angeben, die verwendet werden kann, wenn von einer aufrufenden Prozedur keine Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="93c27-103">Optional parameters must provide default values that can be used if no parameter is supplied by a calling procedure.</span></span>  
  
 <span data-ttu-id="93c27-104">**Fehler-ID:** BC30812</span><span class="sxs-lookup"><span data-stu-id="93c27-104">**Error ID:** BC30812</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="93c27-105">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="93c27-105">To correct this error</span></span>  
  
-   <span data-ttu-id="93c27-106">Angeben von Standardwerten für optionale Parameter; Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="93c27-106">Specify default values for optional parameters; for example:</span></span>  
  
    ```  
    Sub Proc1(ByVal X As Integer,   
          Optional ByVal Y As String = "Default Value")  
       MsgBox("Default argument is: " & Y)  
    End Sub  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="93c27-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="93c27-107">See also</span></span>
- [<span data-ttu-id="93c27-108">Optional</span><span class="sxs-lookup"><span data-stu-id="93c27-108">Optional</span></span>](../../../visual-basic/language-reference/modifiers/optional.md)

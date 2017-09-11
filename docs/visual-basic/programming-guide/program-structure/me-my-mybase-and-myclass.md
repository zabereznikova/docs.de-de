---
title: Me, My, MyBase und MyClass in Visual Basic | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- MyClass
- vb.Me
- MyBase
- vb.MyBase
- Me
- vb.MyClass
- vb.This
- vb.My
dev_langs:
- VB
helpviewer_keywords:
- My object
- self-reference, Me keyword
- MyClass keyword, relationship to similar programming elements
- Me keyword, relationship to similar programming elements
- Me keyword, referring to the current instance of an object
- Me keyword
- self-reference
- current instance, Me keyword
- MyBase keyword, relationship to similar programming elements
ms.assetid: f8e241ae-b1ed-4886-9aa0-08c632154029
caps.latest.revision: 15
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
ms.openlocfilehash: 3ba634eb28c25f47a0e88c856b916383b6ad15a2
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="me-my-mybase-and-myclass-in-visual-basic"></a><span data-ttu-id="141da-102">Me, "My", "MyBase" und "MyClass" in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="141da-102">Me, My, MyBase, and MyClass in Visual Basic</span></span>
<span data-ttu-id="141da-103">`Me`, `My`, `MyBase`, und `MyClass` in [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] verfügen über ähnliche Namen, aber unterschiedlichen Zwecken.</span><span class="sxs-lookup"><span data-stu-id="141da-103">`Me`, `My`, `MyBase`, and `MyClass` in [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] have similar names, but different purposes.</span></span> <span data-ttu-id="141da-104">In diesem Thema wird jede dieser Entitäten beschrieben, um sie voneinander zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="141da-104">This topic describes each of these entities in order to distinguish them.</span></span>  
  
## <a name="me"></a><span data-ttu-id="141da-105">Me</span><span class="sxs-lookup"><span data-stu-id="141da-105">Me</span></span>  
 <span data-ttu-id="141da-106">Die `Me` Schlüsselwort stellt eine Möglichkeit zum Verweisen auf die bestimmte Instanz einer Klasse oder Struktur, in der der Code derzeit ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="141da-106">The `Me` keyword provides a way to refer to the specific instance of a class or structure in which the code is currently executing.</span></span> <span data-ttu-id="141da-107">`Me`verhält sich wie eine Objektvariable oder eine Strukturvariable verweisen auf die aktuelle Instanz.</span><span class="sxs-lookup"><span data-stu-id="141da-107">`Me` behaves like either an object variable or a structure variable referring to the current instance.</span></span> <span data-ttu-id="141da-108">Mithilfe von `Me` ist besonders nützlich für die Übergabe von Informationen über die derzeit ausgeführte Instanz einer Klasse oder Struktur an eine Prozedur in einer anderen Klasse, Struktur oder Modul.</span><span class="sxs-lookup"><span data-stu-id="141da-108">Using `Me` is particularly useful for passing information about the currently executing instance of a class or structure to a procedure in another class, structure, or module.</span></span>  
  
 <span data-ttu-id="141da-109">Nehmen wir beispielsweise an, dass Sie die folgende Prozedur in einem Modul haben.</span><span class="sxs-lookup"><span data-stu-id="141da-109">For example, suppose you have the following procedure in a module.</span></span>  
  
```  
Sub ChangeFormColor(FormName As Form)  
   Randomize()  
   FormName.BackColor = Color.FromArgb(Rnd() * 256, Rnd() * 256, Rnd() * 256)  
End Sub  
```  
  
 <span data-ttu-id="141da-110">Sie können diese Prozedur aufrufen und übergeben die aktuelle Instanz von der <xref:System.Windows.Forms.Form>Klasse als Argument mithilfe der folgenden Anweisung.</xref:System.Windows.Forms.Form></span><span class="sxs-lookup"><span data-stu-id="141da-110">You can call this procedure and pass the current instance of the <xref:System.Windows.Forms.Form> class as an argument by using the following statement.</span></span>  
  
```  
ChangeFormColor(Me)  
```  
  
## <a name="my"></a><span data-ttu-id="141da-111">My</span><span class="sxs-lookup"><span data-stu-id="141da-111">My</span></span>  
 <span data-ttu-id="141da-112">Die `My` Funktion bietet einfachen und intuitiven Zugriff auf eine Anzahl von [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] -Klassen die [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] , mit dem Computer, Anwendung, Einstellungen, Ressourcen usw. interagieren.</span><span class="sxs-lookup"><span data-stu-id="141da-112">The `My` feature provides easy and intuitive access to a number of [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] classes, enabling the [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] user to interact with the computer, application, settings, resources, and so on.</span></span>  
  
## <a name="mybase"></a><span data-ttu-id="141da-113">MyBase</span><span class="sxs-lookup"><span data-stu-id="141da-113">MyBase</span></span>  
 <span data-ttu-id="141da-114">Das `MyBase` -Schlüsselwort verhält sich wie eine Objektvariable verweist auf die Basisklasse der aktuellen Instanz einer Klasse.</span><span class="sxs-lookup"><span data-stu-id="141da-114">The `MyBase` keyword behaves like an object variable referring to the base class of the current instance of a class.</span></span> <span data-ttu-id="141da-115">`MyBase`Member der Basisklasse zugreifen, die überschrieben werden, oder in einer abgeleiteten Klasse gespiegelt wird häufig verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="141da-115">`MyBase` is commonly used to access base class members that are overridden or shadowed in a derived class.</span></span> <span data-ttu-id="141da-116">`MyBase.New`wird verwendet, um einen Basisklassenkonstruktor aus einem abgeleiteten Klassenkonstruktor explizit aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="141da-116">`MyBase.New` is used to explicitly call a base class constructor from a derived class constructor.</span></span>  
  
## <a name="myclass"></a><span data-ttu-id="141da-117">MyClass</span><span class="sxs-lookup"><span data-stu-id="141da-117">MyClass</span></span>  
 <span data-ttu-id="141da-118">Das `MyClass` -Schlüsselwort verhält sich wie eine Objektvariable verweist auf die aktuelle Instanz einer Klasse, die gemäß der ursprünglichen Implementierung.</span><span class="sxs-lookup"><span data-stu-id="141da-118">The `MyClass` keyword behaves like an object variable referring to the current instance of a class as originally implemented.</span></span> <span data-ttu-id="141da-119">`MyClass`ähnelt dem `Me`, aber alle Methodenaufrufe werden behandelt, als wäre die Methode `NotOverridable`.</span><span class="sxs-lookup"><span data-stu-id="141da-119">`MyClass` is similar to `Me`, but all method calls on it are treated as if the method were `NotOverridable`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="141da-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="141da-120">See Also</span></span>  
 [<span data-ttu-id="141da-121">Grundlagen der Vererbung</span><span class="sxs-lookup"><span data-stu-id="141da-121">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)

---
title: Me, "My", "MyBase" und "MyClass" in Visual Basic
ms.date: 07/20/2015
f1_keywords:
- MyClass
- vb.Me
- MyBase
- vb.MyBase
- Me
- vb.MyClass
- vb.This
- vb.My
helpviewer_keywords:
- My object
- self-reference [Visual Basic], Me keyword
- MyClass keyword [Visual Basic], relationship to similar programming elements
- Me keyword [Visual Basic], relationship to similar programming elements
- Me keyword [Visual Basic], referring to the current instance of an object
- Me keyword [Visual Basic]
- self-reference
- current instance [Visual Basic], Me keyword
- MyBase keyword [Visual Basic], relationship to similar programming elements
ms.assetid: f8e241ae-b1ed-4886-9aa0-08c632154029
ms.openlocfilehash: 3eca756429c5fec8f324a17350844b59baf9ccf7
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2019
ms.locfileid: "65586256"
---
# <a name="me-my-mybase-and-myclass-in-visual-basic"></a><span data-ttu-id="270d4-102">Me, "My", "MyBase" und "MyClass" in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="270d4-102">Me, My, MyBase, and MyClass in Visual Basic</span></span>
<span data-ttu-id="270d4-103">`Me`, `My`, `MyBase`, und `MyClass` in Visual Basic zu erhalten, ähnliche Namen, aber unterschiedlichen Zwecken.</span><span class="sxs-lookup"><span data-stu-id="270d4-103">`Me`, `My`, `MyBase`, and `MyClass` in Visual Basic have similar names, but different purposes.</span></span> <span data-ttu-id="270d4-104">Dieses Thema beschreibt jede dieser Entitäten, um sie voneinander zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="270d4-104">This topic describes each of these entities in order to distinguish them.</span></span>  
  
## <a name="me"></a><span data-ttu-id="270d4-105">Me</span><span class="sxs-lookup"><span data-stu-id="270d4-105">Me</span></span>  
 <span data-ttu-id="270d4-106">Die `Me` Schlüsselwort bietet eine Möglichkeit zum Verweisen auf die jeweilige Instanz einer Klasse oder Struktur, die in der der Code derzeit ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="270d4-106">The `Me` keyword provides a way to refer to the specific instance of a class or structure in which the code is currently executing.</span></span> <span data-ttu-id="270d4-107">`Me` verhält sich wie entweder eine Objektvariable oder eine Strukturvariable, die auf die aktuelle Instanz verweist.</span><span class="sxs-lookup"><span data-stu-id="270d4-107">`Me` behaves like either an object variable or a structure variable referring to the current instance.</span></span> <span data-ttu-id="270d4-108">Mithilfe von `Me` ist besonders nützlich für die Übergabe von Informationen über die derzeit ausgeführte Instanz einer Klasse oder Struktur an eine Prozedur in einer anderen Klasse, Struktur oder Moduls.</span><span class="sxs-lookup"><span data-stu-id="270d4-108">Using `Me` is particularly useful for passing information about the currently executing instance of a class or structure to a procedure in another class, structure, or module.</span></span>  
  
 <span data-ttu-id="270d4-109">Nehmen wir beispielsweise an, dass Sie das folgende Verfahren in einem Modul verfügen.</span><span class="sxs-lookup"><span data-stu-id="270d4-109">For example, suppose you have the following procedure in a module.</span></span>  
  
```  
Sub ChangeFormColor(FormName As Form)  
   Randomize()  
   FormName.BackColor = Color.FromArgb(Rnd() * 256, Rnd() * 256, Rnd() * 256)  
End Sub  
```  
  
 <span data-ttu-id="270d4-110">Sie können diese Prozedur aufrufen und übergeben Sie die aktuelle Instanz von der <xref:System.Windows.Forms.Form> Klasse als Argument mithilfe der folgenden Anweisung.</span><span class="sxs-lookup"><span data-stu-id="270d4-110">You can call this procedure and pass the current instance of the <xref:System.Windows.Forms.Form> class as an argument by using the following statement.</span></span>  
  
```  
ChangeFormColor(Me)  
```  
  
## <a name="my"></a><span data-ttu-id="270d4-111">My</span><span class="sxs-lookup"><span data-stu-id="270d4-111">My</span></span>  
 <span data-ttu-id="270d4-112">Die `My` Funktion bietet einfachen und intuitiven Zugriff auf eine Anzahl von .NET Framework-Klassen des Visual Basic-Benutzers für die Interaktion mit der Computer, Anwendung, Einstellungen, Ressourcen und So weiter.</span><span class="sxs-lookup"><span data-stu-id="270d4-112">The `My` feature provides easy and intuitive access to a number of .NET Framework classes, enabling the Visual Basic user to interact with the computer, application, settings, resources, and so on.</span></span>  
  
## <a name="mybase"></a><span data-ttu-id="270d4-113">MyBase</span><span class="sxs-lookup"><span data-stu-id="270d4-113">MyBase</span></span>  
 <span data-ttu-id="270d4-114">Die `MyBase` -Schlüsselwort verhält sich wie eine Objektvariable verweist auf die Basisklasse der aktuellen Instanz einer Klasse.</span><span class="sxs-lookup"><span data-stu-id="270d4-114">The `MyBase` keyword behaves like an object variable referring to the base class of the current instance of a class.</span></span> <span data-ttu-id="270d4-115">`MyBase` Member der Basisklasse zuzugreifen, die überschrieben werden, oder in einer abgeleiteten Klasse schattiert wird häufig verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="270d4-115">`MyBase` is commonly used to access base class members that are overridden or shadowed in a derived class.</span></span> <span data-ttu-id="270d4-116">`MyBase.New` wird verwendet, um explizit einen Basisklassenkonstruktor aus Konstruktor einer abgeleiteten Klasse aufrufen.</span><span class="sxs-lookup"><span data-stu-id="270d4-116">`MyBase.New` is used to explicitly call a base class constructor from a derived class constructor.</span></span>  
  
## <a name="myclass"></a><span data-ttu-id="270d4-117">MyClass</span><span class="sxs-lookup"><span data-stu-id="270d4-117">MyClass</span></span>  
 <span data-ttu-id="270d4-118">Die `MyClass` -Schlüsselwort verhält sich wie eine Objektvariable verweist auf die aktuelle Instanz einer Klasse, wie Sie ursprünglich implementiert.</span><span class="sxs-lookup"><span data-stu-id="270d4-118">The `MyClass` keyword behaves like an object variable referring to the current instance of a class as originally implemented.</span></span> <span data-ttu-id="270d4-119">`MyClass` ist vergleichbar mit `Me`, aber alle zugehörigen Methodenaufrufe werden so behandelt, als wäre die Methode `NotOverridable`.</span><span class="sxs-lookup"><span data-stu-id="270d4-119">`MyClass` is similar to `Me`, but all method calls on it are treated as if the method were `NotOverridable`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="270d4-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="270d4-120">See also</span></span>

- [<span data-ttu-id="270d4-121">Grundlagen der Vererbung</span><span class="sxs-lookup"><span data-stu-id="270d4-121">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)

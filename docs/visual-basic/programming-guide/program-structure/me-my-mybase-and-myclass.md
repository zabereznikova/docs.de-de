---
title: Me, My, MyBase und MyClass
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
ms.openlocfilehash: a21dfeb12e8d99f5f8b8afede084846711c299ab
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347337"
---
# <a name="me-my-mybase-and-myclass-in-visual-basic"></a><span data-ttu-id="8e172-102">Me, "My", "MyBase" und "MyClass" in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8e172-102">Me, My, MyBase, and MyClass in Visual Basic</span></span>
<span data-ttu-id="8e172-103">`Me`, `My`, `MyBase`und `MyClass` in Visual Basic haben ähnliche Namen, aber unterschiedliche Zwecke.</span><span class="sxs-lookup"><span data-stu-id="8e172-103">`Me`, `My`, `MyBase`, and `MyClass` in Visual Basic have similar names, but different purposes.</span></span> <span data-ttu-id="8e172-104">In diesem Thema werden diese Entitäten beschrieben, um Sie zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="8e172-104">This topic describes each of these entities in order to distinguish them.</span></span>  
  
## <a name="me"></a><span data-ttu-id="8e172-105">Me</span><span class="sxs-lookup"><span data-stu-id="8e172-105">Me</span></span>  
 <span data-ttu-id="8e172-106">Das `Me`-Schlüsselwort bietet eine Möglichkeit, auf die jeweilige Instanz einer Klasse oder Struktur zu verweisen, in der der Code gerade ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="8e172-106">The `Me` keyword provides a way to refer to the specific instance of a class or structure in which the code is currently executing.</span></span> <span data-ttu-id="8e172-107">`Me` verhält sich wie eine Objekt Variable oder eine Struktur Variable, die auf die aktuelle Instanz verweist.</span><span class="sxs-lookup"><span data-stu-id="8e172-107">`Me` behaves like either an object variable or a structure variable referring to the current instance.</span></span> <span data-ttu-id="8e172-108">Die Verwendung von `Me` ist besonders nützlich, wenn Informationen über die derzeit ausgeführte Instanz einer Klasse oder Struktur an eine Prozedur in einer anderen Klasse, Struktur oder einem anderen Modul übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="8e172-108">Using `Me` is particularly useful for passing information about the currently executing instance of a class or structure to a procedure in another class, structure, or module.</span></span>  
  
 <span data-ttu-id="8e172-109">Nehmen Sie beispielsweise an, dass Sie das folgende Verfahren in einem Modul ausführen.</span><span class="sxs-lookup"><span data-stu-id="8e172-109">For example, suppose you have the following procedure in a module.</span></span>  
  
```vb  
Sub ChangeFormColor(FormName As Form)  
   Randomize()  
   FormName.BackColor = Color.FromArgb(Rnd() * 256, Rnd() * 256, Rnd() * 256)  
End Sub  
```  
  
 <span data-ttu-id="8e172-110">Sie können diese Prozedur aufzurufen und die aktuelle Instanz der <xref:System.Windows.Forms.Form>-Klasse als Argument übergeben, indem Sie die folgende-Anweisung verwenden.</span><span class="sxs-lookup"><span data-stu-id="8e172-110">You can call this procedure and pass the current instance of the <xref:System.Windows.Forms.Form> class as an argument by using the following statement.</span></span>  
  
```vb  
ChangeFormColor(Me)  
```  
  
## <a name="my"></a><span data-ttu-id="8e172-111">My</span><span class="sxs-lookup"><span data-stu-id="8e172-111">My</span></span>  
 <span data-ttu-id="8e172-112">Das `My` Feature ermöglicht einen einfachen und intuitiven Zugriff auf eine Reihe von .NET Framework Klassen, sodass der Visual Basic Benutzer mit dem Computer, der Anwendung, den Einstellungen, den Ressourcen usw. interagieren kann.</span><span class="sxs-lookup"><span data-stu-id="8e172-112">The `My` feature provides easy and intuitive access to a number of .NET Framework classes, enabling the Visual Basic user to interact with the computer, application, settings, resources, and so on.</span></span>  
  
## <a name="mybase"></a><span data-ttu-id="8e172-113">MyBase</span><span class="sxs-lookup"><span data-stu-id="8e172-113">MyBase</span></span>  
 <span data-ttu-id="8e172-114">Das `MyBase`-Schlüsselwort verhält sich wie eine Objekt Variable, die auf die Basisklasse der aktuellen Instanz einer-Klasse verweist.</span><span class="sxs-lookup"><span data-stu-id="8e172-114">The `MyBase` keyword behaves like an object variable referring to the base class of the current instance of a class.</span></span> <span data-ttu-id="8e172-115">`MyBase` wird häufig verwendet, um auf Basisklassenmember zuzugreifen, die von einer abgeleiteten Klasse überschrieben oder überschattet werden.</span><span class="sxs-lookup"><span data-stu-id="8e172-115">`MyBase` is commonly used to access base class members that are overridden or shadowed in a derived class.</span></span> <span data-ttu-id="8e172-116">`MyBase.New` wird verwendet, um explizit einen Basisklassenkonstruktor aus einem abgeleiteten Klassenkonstruktor aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="8e172-116">`MyBase.New` is used to explicitly call a base class constructor from a derived class constructor.</span></span>  
  
## <a name="myclass"></a><span data-ttu-id="8e172-117">MyClass</span><span class="sxs-lookup"><span data-stu-id="8e172-117">MyClass</span></span>  
 <span data-ttu-id="8e172-118">Das `MyClass`-Schlüsselwort verhält sich wie eine Objekt Variable, die auf die aktuelle Instanz einer Klasse verweist, die ursprünglich implementiert wurde.</span><span class="sxs-lookup"><span data-stu-id="8e172-118">The `MyClass` keyword behaves like an object variable referring to the current instance of a class as originally implemented.</span></span> <span data-ttu-id="8e172-119">`MyClass` ähnelt `Me`, aber alle Methodenaufrufe darauf werden so behandelt, als ob die Methode `NotOverridable`wäre.</span><span class="sxs-lookup"><span data-stu-id="8e172-119">`MyClass` is similar to `Me`, but all method calls on it are treated as if the method were `NotOverridable`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e172-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8e172-120">See also</span></span>

- [<span data-ttu-id="8e172-121">Grundlagen der Vererbung</span><span class="sxs-lookup"><span data-stu-id="8e172-121">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)

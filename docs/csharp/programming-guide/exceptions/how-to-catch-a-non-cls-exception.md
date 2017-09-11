---
title: 'Gewusst wie: Abfangen einer Nicht-CLS-Ausnahme'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- exceptions [C#], non-CLS
ms.assetid: db4630b3-5240-471a-b3a7-c7ff6ab31e8d
caps.latest.revision: 8
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 18a19fe34b8ec13bd9fc6d25335d0931a22ce4a3
ms.contentlocale: de-de
ms.lasthandoff: 09/08/2017

---
# <a name="how-to-catch-a-non-cls-exception"></a><span data-ttu-id="fd2e6-102">Gewusst wie: Abfangen einer Nicht-CLS-Ausnahme</span><span class="sxs-lookup"><span data-stu-id="fd2e6-102">How to: Catch a non-CLS Exception</span></span>
<span data-ttu-id="fd2e6-103">Einige .NET-Sprachen, einschließlich C++/CLI, erlauben Objekten, Ausnahmen auszulösen, die nicht aus <xref:System.Exception> stammen.</span><span class="sxs-lookup"><span data-stu-id="fd2e6-103">Some .NET languages, including C++/CLI, allow objects to throw exceptions that do not derive from <xref:System.Exception>.</span></span> <span data-ttu-id="fd2e6-104">Diese Ausnahmen werden als *Nicht-CLS-Ausnahmen* oder *Nicht-Ausnahmen* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="fd2e6-104">Such exceptions are called *non-CLS exceptions* or *non-Exceptions*.</span></span> <span data-ttu-id="fd2e6-105">In [!INCLUDE[csprcs](~/includes/csprcs-md.md)] können Sie keine Nicht-CLS-Ausnahmen auslösen. Sie können sie jedoch auf zwei Arten abfangen:</span><span class="sxs-lookup"><span data-stu-id="fd2e6-105">In [!INCLUDE[csprcs](~/includes/csprcs-md.md)] you cannot throw non-CLS exceptions, but you can catch them in two ways:</span></span>  
  
-   <span data-ttu-id="fd2e6-106">Innerhalb eines `catch (Exception e)`-Blocks als eine <xref:System.Runtime.CompilerServices.RuntimeWrappedException>.</span><span class="sxs-lookup"><span data-stu-id="fd2e6-106">Within a `catch (Exception e)` block as a <xref:System.Runtime.CompilerServices.RuntimeWrappedException>.</span></span>  
  
     <span data-ttu-id="fd2e6-107">In der Standardeinstellung fängt eine [!INCLUDE[csprcs](~/includes/csprcs-md.md)]-Assembly Nicht-CLS-Ausnahmen als umschlossene Ausnahmen ab.</span><span class="sxs-lookup"><span data-stu-id="fd2e6-107">By default, a [!INCLUDE[csprcs](~/includes/csprcs-md.md)] assembly catches non-CLS exceptions as wrapped exceptions.</span></span> <span data-ttu-id="fd2e6-108">Verwenden Sie diese Methode, wenn Sie Zugriff auf die ursprüngliche Ausnahme benötigen, auf die über die Eigenschaft <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A> zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="fd2e6-108">Use this method if you need access to the original exception, which can be accessed through the <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A> property.</span></span> <span data-ttu-id="fd2e6-109">Weiter unten in diesem Thema wird erläutert, wie Abfragen auf diese Art und Weise abgefangen werden können.</span><span class="sxs-lookup"><span data-stu-id="fd2e6-109">The procedure later in this topic explains how to catch exceptions in this manner.</span></span>  
  
-   <span data-ttu-id="fd2e6-110">Innerhalb eines allgemeinen Catch-Blocks (ein Catch-Block ohne angegebenen Ausnahmetyp), der nach einem `catch (Exception)`- oder `catch (Exception e)`-Block eingefügt wird.</span><span class="sxs-lookup"><span data-stu-id="fd2e6-110">Within a general catch block (a catch block without an exception type specified) that is put after a `catch (Exception)` or `catch (Exception e)` block.</span></span>  
  
     <span data-ttu-id="fd2e6-111">Verwenden Sie diese Methode, wenn Sie eine Aktion (z.B. das Schreiben in eine Protokolldatei) als Reaktion auf Nicht-CLS-Ausnahmen ausführen möchten und Sie keinen Zugriff auf die Ausnahmeinformationen benötigen.</span><span class="sxs-lookup"><span data-stu-id="fd2e6-111">Use this method when you want to perform some action (such as writing to a log file) in response to non-CLS exceptions, and you do not need access to the exception information.</span></span> <span data-ttu-id="fd2e6-112">Standardmäßig umschließt die Common Language Runtime alle Ausnahmen.</span><span class="sxs-lookup"><span data-stu-id="fd2e6-112">By default the common language runtime wraps all exceptions.</span></span> <span data-ttu-id="fd2e6-113">Um dieses Verhalten zu deaktivieren, fügen Sie dieses Attribut auf Assemblyebene Ihrem Code hinzu, in der Regel in die Datei „AssemblyInfo.cs“: `[assembly: RuntimeCompatibilityAttribute(WrapNonExceptionThrows = false)]`.</span><span class="sxs-lookup"><span data-stu-id="fd2e6-113">To disable this behavior, add this assembly-level attribute to your code, typically in the AssemblyInfo.cs file: `[assembly: RuntimeCompatibilityAttribute(WrapNonExceptionThrows = false)]`.</span></span>  
  
### <a name="to-catch-a-non-cls-exception"></a><span data-ttu-id="fd2e6-114">So fangen Sie eine Nicht-CLS-Ausnahme ab</span><span class="sxs-lookup"><span data-stu-id="fd2e6-114">To catch a non-CLS exception</span></span>  
  
1.  <span data-ttu-id="fd2e6-115">Verwenden Sie innerhalb von `catch(Exception e) block` das Schlüsselwort `as`, um zu testen, ob `e` in eine <xref:System.Runtime.CompilerServices.RuntimeWrappedException> umgewandelt werden kann.</span><span class="sxs-lookup"><span data-stu-id="fd2e6-115">Within a `catch(Exception e) block`, use the `as` keyword to test whether `e` can be cast to a <xref:System.Runtime.CompilerServices.RuntimeWrappedException>.</span></span>  
  
2.  <span data-ttu-id="fd2e6-116">Greifen Sie über die Eigenschaft <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A> auf die ursprüngliche Ausnahme zu.</span><span class="sxs-lookup"><span data-stu-id="fd2e6-116">Access the original exception through the <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fd2e6-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fd2e6-117">Example</span></span>  
 <span data-ttu-id="fd2e6-118">Das folgende Beispiel zeigt, wie Sie eine Nicht-CLS-Ausnahme abfangen, die von einer in C++/CRL geschriebenen Klassenbibliothek ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="fd2e6-118">The following example shows how to catch a non-CLS exception that was thrown from a class library written in C++/CLR.</span></span> <span data-ttu-id="fd2e6-119">Beachten Sie, dass in diesem Beispiel der [!INCLUDE[csprcs](~/includes/csprcs-md.md)]-Clientcode im Voraus weiß, dass der Ausnahmetyp, der ausgelöst wird, eine <xref:System.String?displayProperty=fullName> darstellt.</span><span class="sxs-lookup"><span data-stu-id="fd2e6-119">Note that in this example, the [!INCLUDE[csprcs](~/includes/csprcs-md.md)] client code knows in advance that the exception type being thrown is a <xref:System.String?displayProperty=fullName>.</span></span> <span data-ttu-id="fd2e6-120">Wandeln Sie die Eigenschaft <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A> in den ursprünglichen Typ um, solange dieser Typ über Ihren Code erreicht werden kann.</span><span class="sxs-lookup"><span data-stu-id="fd2e6-120">You can cast the <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A> property back its original type as long as that type is accessible from your code.</span></span>  
  
```  
// Class library written in C++/CLR.  
   ThrowNonCLS.Class1 myClass = new ThrowNonCLS.Class1();  
  
   try  
   {  
    // throws gcnew System::String(  
    // "I do not derive from System.Exception!");  
    myClass.TestThrow();   
   }  
  
   catch (Exception e)  
   {  
    RuntimeWrappedException rwe = e as RuntimeWrappedException;  
    if (rwe != null)      
    {  
      String s = rwe.WrappedException as String;  
      if (s != null)  
      {  
        Console.WriteLine(s);  
      }  
    }  
    else  
    {  
       // Handle other System.Exception types.  
    }  
   }             
```  
  
## <a name="see-also"></a><span data-ttu-id="fd2e6-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fd2e6-121">See Also</span></span>  
 <span data-ttu-id="fd2e6-122"><xref:System.Runtime.CompilerServices.RuntimeWrappedException></span><span class="sxs-lookup"><span data-stu-id="fd2e6-122"><xref:System.Runtime.CompilerServices.RuntimeWrappedException></span></span>   
 [<span data-ttu-id="fd2e6-123">Ausnahmen und Ausnahmebehandlung</span><span class="sxs-lookup"><span data-stu-id="fd2e6-123">Exceptions and Exception Handling</span></span>](../../../csharp/programming-guide/exceptions/index.md)


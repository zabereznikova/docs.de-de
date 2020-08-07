---
title: Abfangen einer Nicht-CLS-Ausnahme
description: Erfahren Sie, wie Sie eine Nicht-CLS-Ausnahme abfangen. Hier finden Sie ein Codebeispiel und zusätzliche verfügbare Ressourcen.
ms.date: 07/20/2015
helpviewer_keywords:
- exceptions [C#], non-CLS
ms.assetid: db4630b3-5240-471a-b3a7-c7ff6ab31e8d
ms.openlocfilehash: 255de4cab9a72491eb3b9624d968539d432e0442
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302008"
---
# <a name="how-to-catch-a-non-cls-exception"></a><span data-ttu-id="986a0-104">Abfangen einer Nicht-CLS-Ausnahme</span><span class="sxs-lookup"><span data-stu-id="986a0-104">How to catch a non-CLS exception</span></span>
<span data-ttu-id="986a0-105">Einige .NET-Sprachen, einschließlich C++/CLI, erlauben Objekten, Ausnahmen auszulösen, die nicht aus <xref:System.Exception> stammen.</span><span class="sxs-lookup"><span data-stu-id="986a0-105">Some .NET languages, including C++/CLI, allow objects to throw exceptions that do not derive from <xref:System.Exception>.</span></span> <span data-ttu-id="986a0-106">Diese Ausnahmen werden als *Nicht-CLS-Ausnahmen* oder *Nicht-Ausnahmen* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="986a0-106">Such exceptions are called *non-CLS exceptions* or *non-Exceptions*.</span></span> <span data-ttu-id="986a0-107">In C# können Sie keine Nicht-CLS-Ausnahmen auslösen. Sie können sie jedoch auf zwei Arten abfangen:</span><span class="sxs-lookup"><span data-stu-id="986a0-107">In C# you cannot throw non-CLS exceptions, but you can catch them in two ways:</span></span>  
  
- <span data-ttu-id="986a0-108">Innerhalb eines `catch (RuntimeWrappedException e)`-Blocks</span><span class="sxs-lookup"><span data-stu-id="986a0-108">Within a `catch (RuntimeWrappedException e)` block.</span></span>
  
     <span data-ttu-id="986a0-109">In der Standardeinstellung fängt eine Visual C#-Assembly Nicht-CLS-Ausnahmen als umschlossene Ausnahmen ab.</span><span class="sxs-lookup"><span data-stu-id="986a0-109">By default, a Visual C# assembly catches non-CLS exceptions as wrapped exceptions.</span></span> <span data-ttu-id="986a0-110">Verwenden Sie diese Methode, wenn Sie Zugriff auf die ursprüngliche Ausnahme benötigen, auf die über die Eigenschaft <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A?displayProperty=nameWithType> zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="986a0-110">Use this method if you need access to the original exception, which can be accessed through the <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="986a0-111">Weiter unten in diesem Thema wird erläutert, wie Abfragen auf diese Art und Weise abgefangen werden können.</span><span class="sxs-lookup"><span data-stu-id="986a0-111">The procedure later in this topic explains how to catch exceptions in this manner.</span></span>  
  
- <span data-ttu-id="986a0-112">Innerhalb eines allgemeinen Catch-Blocks (ein Catch-Block ohne angegebenen Ausnahmetyp), der nach allen anderen `catch`-Blocks eingefügt wird</span><span class="sxs-lookup"><span data-stu-id="986a0-112">Within a general catch block (a catch block without an exception type specified) that is put after all other `catch` blocks.</span></span>
  
     <span data-ttu-id="986a0-113">Verwenden Sie diese Methode, wenn Sie eine Aktion (z.B. das Schreiben in eine Protokolldatei) als Reaktion auf Nicht-CLS-Ausnahmen ausführen möchten und Sie keinen Zugriff auf die Ausnahmeinformationen benötigen.</span><span class="sxs-lookup"><span data-stu-id="986a0-113">Use this method when you want to perform some action (such as writing to a log file) in response to non-CLS exceptions, and you do not need access to the exception information.</span></span> <span data-ttu-id="986a0-114">Standardmäßig umschließt die Common Language Runtime alle Ausnahmen.</span><span class="sxs-lookup"><span data-stu-id="986a0-114">By default the common language runtime wraps all exceptions.</span></span> <span data-ttu-id="986a0-115">Um dieses Verhalten zu deaktivieren, fügen Sie dieses Attribut auf Assemblyebene Ihrem Code hinzu, in der Regel in die Datei „AssemblyInfo.cs“: `[assembly: RuntimeCompatibilityAttribute(WrapNonExceptionThrows = false)]`.</span><span class="sxs-lookup"><span data-stu-id="986a0-115">To disable this behavior, add this assembly-level attribute to your code, typically in the AssemblyInfo.cs file: `[assembly: RuntimeCompatibilityAttribute(WrapNonExceptionThrows = false)]`.</span></span>  
  
### <a name="to-catch-a-non-cls-exception"></a><span data-ttu-id="986a0-116">So fangen Sie eine Nicht-CLS-Ausnahme ab</span><span class="sxs-lookup"><span data-stu-id="986a0-116">To catch a non-CLS exception</span></span>  
  
<span data-ttu-id="986a0-117">Greifen Sie in einem `catch(RuntimeWrappedException e)`-Block über die Eigenschaft <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A?displayProperty=nameWithType> auf die ursprüngliche Ausnahme zu.</span><span class="sxs-lookup"><span data-stu-id="986a0-117">Within a `catch(RuntimeWrappedException e)` block, access the original exception through the <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="986a0-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="986a0-118">Example</span></span>  
 <span data-ttu-id="986a0-119">Im folgenden Beispiel wird gezeigt, wie Sie eine Nicht-CLS-Ausnahme abfangen, die von einer in C++/CLI geschriebenen Klassenbibliothek ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="986a0-119">The following example shows how to catch a non-CLS exception that was thrown from a class library written in C++/CLI.</span></span> <span data-ttu-id="986a0-120">Beachten Sie, dass in diesem Beispiel der C#-Clientcode im Voraus weiß, dass der Ausnahmetyp, der ausgelöst wird, <xref:System.String?displayProperty=nameWithType> lautet.</span><span class="sxs-lookup"><span data-stu-id="986a0-120">Note that in this example, the C# client code knows in advance that the exception type being thrown is a <xref:System.String?displayProperty=nameWithType>.</span></span> <span data-ttu-id="986a0-121">Wandeln Sie die Eigenschaft <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A?displayProperty=nameWithType> in den ursprünglichen Typ um, solange dieser Typ über Ihren Code erreicht werden kann.</span><span class="sxs-lookup"><span data-stu-id="986a0-121">You can cast the <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A?displayProperty=nameWithType> property back its original type as long as that type is accessible from your code.</span></span>  
  
```csharp
// Class library written in C++/CLI.
var myClass = new ThrowNonCLS.Class1();

try
{
    // throws gcnew System::String(  
    // "I do not derive from System.Exception!");  
    myClass.TestThrow();
}
catch (RuntimeWrappedException e)
{
    String s = e.WrappedException as String;
    if (s != null)
    {
        Console.WriteLine(s);
    }
}
```  
  
## <a name="see-also"></a><span data-ttu-id="986a0-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="986a0-122">See also</span></span>

- <xref:System.Runtime.CompilerServices.RuntimeWrappedException>
- [<span data-ttu-id="986a0-123">Ausnahmen und Ausnahmebehandlung</span><span class="sxs-lookup"><span data-stu-id="986a0-123">Exceptions and Exception Handling</span></span>](./index.md)

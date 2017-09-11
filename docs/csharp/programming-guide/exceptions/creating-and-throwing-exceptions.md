---
title: "Erstellen und Auslösen von Ausnahmen (C#-Programmierhandbuch)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- catching exceptions [C#]
- throwing exceptions [C#]
- exceptions [C#], creating
- exceptions [C#], throwing
ms.assetid: 6bbba495-a115-4c6d-90cc-1f4d7b5f39e2
caps.latest.revision: 28
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
ms.openlocfilehash: 5f49b0911aa94480988987f209bc73d187451620
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="creating-and-throwing-exceptions-c-programming-guide"></a><span data-ttu-id="8f0f0-102">Erstellen und Auslösen von Ausnahmen (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="8f0f0-102">Creating and Throwing Exceptions (C# Programming Guide)</span></span>
<span data-ttu-id="8f0f0-103">Ausnahmen werden verwendet, um anzugeben, dass während der Ausführung des Programms ein Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="8f0f0-103">Exceptions are used to indicate that an error has occurred while running the program.</span></span> <span data-ttu-id="8f0f0-104">Ausnahmeobjekte, die einen Fehler beschreiben, werden erstellt und dann mit dem Schlüsselwort [throw](../../../csharp/language-reference/keywords/throw.md) (auslösen) *ausgelöst*.</span><span class="sxs-lookup"><span data-stu-id="8f0f0-104">Exception objects that describe an error are created and then *thrown* with the [throw](../../../csharp/language-reference/keywords/throw.md) keyword.</span></span> <span data-ttu-id="8f0f0-105">Die Laufzeit sucht dann nach dem kompatibelsten Ausnahmehandler.</span><span class="sxs-lookup"><span data-stu-id="8f0f0-105">The runtime then searches for the most compatible exception handler.</span></span>  
  
 <span data-ttu-id="8f0f0-106">Programmierer sollten Ausnahmen auslösen, wenn eine oder mehrere der folgenden Bedingungen wahr sind:</span><span class="sxs-lookup"><span data-stu-id="8f0f0-106">Programmers should throw exceptions when one or more of the following conditions are true:</span></span>  
  
-   <span data-ttu-id="8f0f0-107">Die Methode kann deren definierte Funktionalität nicht abschließen.</span><span class="sxs-lookup"><span data-stu-id="8f0f0-107">The method cannot complete its defined functionality.</span></span>  
  
     <span data-ttu-id="8f0f0-108">Wenn beispielsweise ein Parameter einer Methode einen ungültigen Wert hat:</span><span class="sxs-lookup"><span data-stu-id="8f0f0-108">For example, if a parameter to a method has an invalid value:</span></span>  
  
     <span data-ttu-id="8f0f0-109">[!code-cs[csProgGuideExceptions#12](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/creating-and-throwing-exceptions_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="8f0f0-109">[!code-cs[csProgGuideExceptions#12](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/creating-and-throwing-exceptions_1.cs)]</span></span>  
  
-   <span data-ttu-id="8f0f0-110">Ein unpassender Aufruf eines Objekts erfolgt, basierend auf dem Objektzustand.</span><span class="sxs-lookup"><span data-stu-id="8f0f0-110">An inappropriate call to an object is made, based on the object state.</span></span>  
  
     <span data-ttu-id="8f0f0-111">Ein Beispiel wäre ein Versuch, in eine schreibgeschützte Datei zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="8f0f0-111">One example might be trying to write to a read-only file.</span></span> <span data-ttu-id="8f0f0-112">Lösen Sie in Fällen, in denen ein Objektzustand keinen Vorgang erlaubt, eine Instanz von <xref:System.InvalidOperationException> oder ein Objekt aus, das auf einer Ableitung dieser Klasse basiert.</span><span class="sxs-lookup"><span data-stu-id="8f0f0-112">In cases where an object state does not allow an operation, throw an instance of <xref:System.InvalidOperationException> or an object based on a derivation of this class.</span></span> <span data-ttu-id="8f0f0-113">Dies ist ein Beispiel für eine Methode, die eine <xref:System.InvalidOperationException> auslöst:</span><span class="sxs-lookup"><span data-stu-id="8f0f0-113">This is an example of a method that throws an <xref:System.InvalidOperationException> object:</span></span>  
  
     <span data-ttu-id="8f0f0-114">[!code-cs[csProgGuideExceptions#13](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/creating-and-throwing-exceptions_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="8f0f0-114">[!code-cs[csProgGuideExceptions#13](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/creating-and-throwing-exceptions_2.cs)]</span></span>  
  
-   <span data-ttu-id="8f0f0-115">Wenn ein Argument an eine Methode eine Ausnahme auslöst.</span><span class="sxs-lookup"><span data-stu-id="8f0f0-115">When an argument to a method causes an exception.</span></span>  
  
     <span data-ttu-id="8f0f0-116">In diesem Fall muss die ursprüngliche Ausnahme abgefangen und eine <xref:System.ArgumentException>-Instanz erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="8f0f0-116">In this case, the original exception should be caught and an <xref:System.ArgumentException> instance should be created.</span></span> <span data-ttu-id="8f0f0-117">Die ursprüngliche Ausnahme sollte an den Konstruktor der <xref:System.ArgumentException> als <xref:System.Exception.InnerException%2A>-Parameter übergeben werden:</span><span class="sxs-lookup"><span data-stu-id="8f0f0-117">The original exception should be passed to the constructor of the <xref:System.ArgumentException> as the <xref:System.Exception.InnerException%2A> parameter:</span></span>  
  
     <span data-ttu-id="8f0f0-118">[!code-cs[csProgGuideExceptions#14](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/creating-and-throwing-exceptions_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="8f0f0-118">[!code-cs[csProgGuideExceptions#14](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/creating-and-throwing-exceptions_3.cs)]</span></span>  
  
 <span data-ttu-id="8f0f0-119">Ausnahmen enthalten eine Eigenschaft mit dem Namen <xref:System.Exception.StackTrace%2A>.</span><span class="sxs-lookup"><span data-stu-id="8f0f0-119">Exceptions contain a property named <xref:System.Exception.StackTrace%2A>.</span></span> <span data-ttu-id="8f0f0-120">Diese Zeichenfolge enthält den Namen der Methoden für die aktuelle Aufrufliste, zusammen mit dem Dateinamen und der Zeilennummer, in der die Ausnahme für jede Methode ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="8f0f0-120">This string contains the name of the methods on the current call stack, together with the file name and line number where the exception was thrown for each method.</span></span> <span data-ttu-id="8f0f0-121">Ein <xref:System.Exception.StackTrace%2A>-Objekt wird automatisch von der Common Language Runtime (CLR) ab der `throw`-Anweisung erstellt, sodass Ausnahmen ab dem Punkt ausgelöst werden müssen, an dem die Stapelüberwachung beginnen soll.</span><span class="sxs-lookup"><span data-stu-id="8f0f0-121">A <xref:System.Exception.StackTrace%2A> object is created automatically by the common language runtime (CLR) from the point of the `throw` statement, so that exceptions must be thrown from the point where the stack trace should begin.</span></span>  
  
 <span data-ttu-id="8f0f0-122">Alle Ausnahmen enthalten eine Eigenschaft mit dem Namen <xref:System.Exception.Message%2A>.</span><span class="sxs-lookup"><span data-stu-id="8f0f0-122">All exceptions contain a property named <xref:System.Exception.Message%2A>.</span></span> <span data-ttu-id="8f0f0-123">Diese Zeichenfolge sollte festgelegt werden, um die Gründe für die Ausnahme zu erklären.</span><span class="sxs-lookup"><span data-stu-id="8f0f0-123">This string should be set to explain the reason for the exception.</span></span> <span data-ttu-id="8f0f0-124">Beachten Sie, dass vertrauliche Informationen aus Sicherheitsgründen nicht im E-Mail-Text eingefügt werden dürfen.</span><span class="sxs-lookup"><span data-stu-id="8f0f0-124">Note that information that is sensitive to security should not be put in the message text.</span></span> <span data-ttu-id="8f0f0-125">Zusätzlich zu <xref:System.Exception.Message%2A> enthält <xref:System.ArgumentException> eine Eigenschaft mit dem Namen <xref:System.ArgumentException.ParamName%2A>, die auf den Namen des Arguments festgelegt werden sollte, das die Ausnahme ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="8f0f0-125">In addition to <xref:System.Exception.Message%2A>, <xref:System.ArgumentException> contains a property named <xref:System.ArgumentException.ParamName%2A> that should be set to the name of the argument that caused the exception to be thrown.</span></span> <span data-ttu-id="8f0f0-126">Im Falle eines Eigenschaftensetters sollte <xref:System.ArgumentException.ParamName%2A> auf `value` festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="8f0f0-126">In the case of a property setter, <xref:System.ArgumentException.ParamName%2A> should be set to `value`.</span></span>  
  
 <span data-ttu-id="8f0f0-127">Öffentliche und geschützte Methodenmember sollten Ausnahmen auslösen, wann immer sie ihre beabsichtigten Funktionen nicht auslösen können.</span><span class="sxs-lookup"><span data-stu-id="8f0f0-127">Public and protected methods members should throw exceptions whenever they cannot complete their intended functions.</span></span> <span data-ttu-id="8f0f0-128">Die Ausnahmeklasse, die ausgelöst wird, muss die möglichst genaueste verfügbare Ausnahme sein, die zu den Fehlerbedingungen passt.</span><span class="sxs-lookup"><span data-stu-id="8f0f0-128">The exception class that is thrown should be the most specific exception available that fits the error conditions.</span></span> <span data-ttu-id="8f0f0-129">Diese Ausnahmen sollten als Teil der Klassenfunktionalität dokumentiert werden, und abgeleitete Klassen oder Updates an der ursprünglichen Klasse müssen das gleiche Verhalten für die Abwärtskompatibilität beibehalten.</span><span class="sxs-lookup"><span data-stu-id="8f0f0-129">These exceptions should be documented as part of the class functionality, and derived classes or updates to the original class should retain the same behavior for backward compatibility.</span></span>  
  
## <a name="things-to-avoid-when-throwing-exceptions"></a><span data-ttu-id="8f0f0-130">Was Sie beim Auslösen von Ausnahmen vermeiden sollten</span><span class="sxs-lookup"><span data-stu-id="8f0f0-130">Things to Avoid When Throwing Exceptions</span></span>  
 <span data-ttu-id="8f0f0-131">Die folgende Liste enthält Vorgehensweisen, die beim Auslösen von Ausnahmen zu vermeiden sind:</span><span class="sxs-lookup"><span data-stu-id="8f0f0-131">The following list identifies practices to avoid when throwing exceptions:</span></span>  
  
-   <span data-ttu-id="8f0f0-132">Ausnahmen dürfen nicht zum Ändern des Flusses eines Programms als Teil der normalen Ausführung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8f0f0-132">Exceptions should not be used to change the flow of a program as part of ordinary execution.</span></span> <span data-ttu-id="8f0f0-133">Ausnahmen dürfen nur zum Melden und Behandeln von Fehlerzuständen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8f0f0-133">Exceptions should only be used to report and handle error conditions.</span></span>  
  
-   <span data-ttu-id="8f0f0-134">Ausnahmen dürfen nicht als Rückgabewert oder Parameter zurückgegeben werden, anstatt ausgelöst zu werden.</span><span class="sxs-lookup"><span data-stu-id="8f0f0-134">Exceptions should not be returned as a return value or parameter instead of being thrown.</span></span>  
  
-   <span data-ttu-id="8f0f0-135">Lösen Sie <xref:System.Exception?displayProperty=fullName>, <xref:System.SystemException?displayProperty=fullName>, <xref:System.NullReferenceException?displayProperty=fullName> oder <xref:System.IndexOutOfRangeException?displayProperty=fullName> nicht mit Absicht über Ihren eigenen Quellcode aus.</span><span class="sxs-lookup"><span data-stu-id="8f0f0-135">Do not throw <xref:System.Exception?displayProperty=fullName>, <xref:System.SystemException?displayProperty=fullName>, <xref:System.NullReferenceException?displayProperty=fullName>, or <xref:System.IndexOutOfRangeException?displayProperty=fullName> intentionally from your own source code.</span></span>  
  
-   <span data-ttu-id="8f0f0-136">Erstellen Sie keine Ausnahmen, die im Debugmodus, aber nicht im Releasemodus ausgelöst werden können.</span><span class="sxs-lookup"><span data-stu-id="8f0f0-136">Do not create exceptions that can be thrown in debug mode but not release mode.</span></span> <span data-ttu-id="8f0f0-137">Um Laufzeitfehler während der Entwicklungsphase zu identifizieren, verwenden Sie stattdessen die Debugassertion.</span><span class="sxs-lookup"><span data-stu-id="8f0f0-137">To identify run-time errors during the development phase, use Debug Assert instead.</span></span>  
  
## <a name="defining-exception-classes"></a><span data-ttu-id="8f0f0-138">Definieren von Ausnahmeklassen</span><span class="sxs-lookup"><span data-stu-id="8f0f0-138">Defining Exception Classes</span></span>  
 <span data-ttu-id="8f0f0-139">Programme können eine zuvor definierte Ausnahmeklasse im <xref:System>-Namespace auslösen (mit Ausnahme der eben beschriebenen Fälle) oder ihre eigenen Ausnahmeklassen durch Ableitung von <xref:System.Exception> erstellen.</span><span class="sxs-lookup"><span data-stu-id="8f0f0-139">Programs can throw a predefined exception class in the <xref:System> namespace (except where previously noted), or create their own exception classes by deriving from <xref:System.Exception>.</span></span> <span data-ttu-id="8f0f0-140">Die abgeleiteten Klassen müssen zumindest vier Konstruktoren definieren: einen Standardkonstruktor, einen, der die message-Eigenschaft festlegt, und einen, der jeweils die Eigenschaften <xref:System.Exception.Message%2A> und <xref:System.Exception.InnerException%2A> festlegt.</span><span class="sxs-lookup"><span data-stu-id="8f0f0-140">The derived classes should define at least four constructors: one default constructor, one that sets the message property, and one that sets both the <xref:System.Exception.Message%2A> and <xref:System.Exception.InnerException%2A> properties.</span></span> <span data-ttu-id="8f0f0-141">Der vierte Konstruktor wird verwendet, um die Ausnahme zu serialisieren.</span><span class="sxs-lookup"><span data-stu-id="8f0f0-141">The fourth constructor is used to serialize the exception.</span></span> <span data-ttu-id="8f0f0-142">Neue Ausnahmeklassen sollten serialisierbar sein.</span><span class="sxs-lookup"><span data-stu-id="8f0f0-142">New exception classes should be serializable.</span></span> <span data-ttu-id="8f0f0-143">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="8f0f0-143">For example:</span></span>  
  
 <span data-ttu-id="8f0f0-144">[!code-cs[csProgGuideExceptions#15](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/creating-and-throwing-exceptions_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="8f0f0-144">[!code-cs[csProgGuideExceptions#15](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/creating-and-throwing-exceptions_4.cs)]</span></span>  
  
 <span data-ttu-id="8f0f0-145">Neue Eigenschaften sollten nur zur Ausnahmeklasse hinzugefügt werden, wenn die Daten, die sie bereitstellen, zur Auflösung der Ausnahme nützlich sind.</span><span class="sxs-lookup"><span data-stu-id="8f0f0-145">New properties should only be added to the exception class when the data they provide is useful to resolving the exception.</span></span> <span data-ttu-id="8f0f0-146">Wenn der abgeleiteten Ausnahmeklasse neue Eigenschaften hinzugefügt werden, muss `ToString()` überschrieben werden, um die hinzugefügten Informationen zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="8f0f0-146">If new properties are added to the derived exception class, `ToString()` should be overridden to return the added information.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="8f0f0-147">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="8f0f0-147">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8f0f0-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8f0f0-148">See Also</span></span>  
 <span data-ttu-id="8f0f0-149">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="8f0f0-149">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="8f0f0-150">[Ausnahmen und Ausnahmebehandlung](../../../csharp/programming-guide/exceptions/index.md) </span><span class="sxs-lookup"><span data-stu-id="8f0f0-150">[Exceptions and Exception Handling](../../../csharp/programming-guide/exceptions/index.md) </span></span>  
 <span data-ttu-id="8f0f0-151">[Ausnahmenhierarchie](http://msdn.microsoft.com/library/f7d68675-be06-40fb-a555-05f0c5a6f66b) </span><span class="sxs-lookup"><span data-stu-id="8f0f0-151">[Exception Hierarchy](http://msdn.microsoft.com/library/f7d68675-be06-40fb-a555-05f0c5a6f66b) </span></span>  
 [<span data-ttu-id="8f0f0-152">Ausnahmebehandlung</span><span class="sxs-lookup"><span data-stu-id="8f0f0-152">Exception Handling</span></span>](../../../csharp/programming-guide/exceptions/exception-handling.md)


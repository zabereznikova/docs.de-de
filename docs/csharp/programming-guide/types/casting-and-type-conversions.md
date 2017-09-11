---
title: Umwandlung und Typkonvertierungen (C#-Programmierhandbuch)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- type conversion [C#]
- data type conversion [C#]
- numeric conversions [C#]
- conversions [C#], type
- casting [C#]
- converting types [C#]
ms.assetid: 568df58a-d292-4b55-93ba-601578722878
caps.latest.revision: 52
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
ms.openlocfilehash: 20743c07c8e9c6b7ec24cf52a28bb9f451ba9df5
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="casting-and-type-conversions-c-programming-guide"></a><span data-ttu-id="7aa81-102">Umwandlung und Typkonvertierungen (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="7aa81-102">Casting and Type Conversions (C# Programming Guide)</span></span>
<span data-ttu-id="7aa81-103">Weil C# zur Laufzeit statisch kompiliert ist, kann eine Variable, nachdem sie deklariert wurde, nicht noch einmal deklariert oder dazu verwendet werden, Werte anderer Typen zu speichern, es sei denn, der Wert ist in den Wert der Variablen konvertierbar.</span><span class="sxs-lookup"><span data-stu-id="7aa81-103">Because C# is statically-typed at compile time, after a variable is declared, it cannot be declared again or used to store values of another type unless that type is convertible to the variable's type.</span></span> <span data-ttu-id="7aa81-104">Es gibt z.B. keine Konvertierung einer Ganzzahl in eine willkürliche Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="7aa81-104">For example, there is no conversion from an integer to any arbitrary string.</span></span> <span data-ttu-id="7aa81-105">Deshalb können Sie, nachdem Sie `i` Ganzzahl deklariert haben, die Zeichenfolge „Hello“ nicht zuweisen, wie in folgendem Codebeispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="7aa81-105">Therefore, after you declare `i` as an integer, you cannot assign the string "Hello" to it, as is shown in the following code.</span></span>  
  
```csharp  
int i;  
i = "Hello"; // Error: "Cannot implicitly convert type 'string' to 'int'"  
```  
  
 <span data-ttu-id="7aa81-106">Manchmal müssen Sie möglicherweise einen Wert in eine Variable oder einen Methodenparameter eines anderen Typen kopieren.</span><span class="sxs-lookup"><span data-stu-id="7aa81-106">However, you might sometimes need to copy a value into a variable or method parameter of another type.</span></span> <span data-ttu-id="7aa81-107">Sie haben z.B. möglicherweise eine Ganzzahlvariable, die Sie an eine Methode übergeben müssen, deren Parameter vom Type `double` ist.</span><span class="sxs-lookup"><span data-stu-id="7aa81-107">For example, you might have an integer variable that you need to pass to a method whose parameter is typed as `double`.</span></span> <span data-ttu-id="7aa81-108">Möglicherweise müssen Sie auch einer Variablen eines Schnittstellentyps eine Klassenvariable zuweisen.</span><span class="sxs-lookup"><span data-stu-id="7aa81-108">Or you might need to assign a class variable to a variable of an interface type.</span></span> <span data-ttu-id="7aa81-109">Derartige Vorgänge werden als *Typkonvertierungen* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="7aa81-109">These kinds of operations are called *type conversions*.</span></span> <span data-ttu-id="7aa81-110">In C# können Sie folgende Arten von Konvertierungen durchführen:</span><span class="sxs-lookup"><span data-stu-id="7aa81-110">In C#, you can perform the following kinds of conversions:</span></span>  
  
-   <span data-ttu-id="7aa81-111">**Implizite Konvertierung**: Es ist keine besondere Syntax erforderlich, da die Konvertierung typsicher ist, und keine Daten verloren gehen.</span><span class="sxs-lookup"><span data-stu-id="7aa81-111">**Implicit conversions**: No special syntax is required because the conversion is type safe and no data will be lost.</span></span> <span data-ttu-id="7aa81-112">Beispiele sind Konvertierungen von kleinere in größere Ganzzahltypen und Konvertierungen von abgeleiteten in Basisklassen.</span><span class="sxs-lookup"><span data-stu-id="7aa81-112">Examples include conversions from smaller to larger integral types, and conversions from derived classes to base classes.</span></span>  
  
-   <span data-ttu-id="7aa81-113">**Explizite Konvertierungen (Umwandlungen)**: Für explizite Konvertierungen ist ein Umwandlungsoperator erforderlich.</span><span class="sxs-lookup"><span data-stu-id="7aa81-113">**Explicit conversions (casts)**: Explicit conversions require a cast operator.</span></span> <span data-ttu-id="7aa81-114">Eine Umwandlung ist erforderlich, wenn Informationen bei einer Konvertierung verloren gehen können oder wenn die Konvertierung aus anderen Gründen fehlschlagen könnte.</span><span class="sxs-lookup"><span data-stu-id="7aa81-114">Casting is required when information might be lost in the conversion, or when the conversion might not succeed for other reasons.</span></span>  <span data-ttu-id="7aa81-115">Häufig auftretende Beispiele sind u.a. numerische Konvertierungen in einen Typen, der eine geringere Genauigkeit oder einen kleineren Bereich aufweist, oder Konvertierungen einer Instanz einer Basisklasse in eine abgeleitete Klasse.</span><span class="sxs-lookup"><span data-stu-id="7aa81-115">Typical examples include numeric conversion to a type that has less precision or a smaller range, and conversion of a base-class instance to a derived class.</span></span>  
  
-   <span data-ttu-id="7aa81-116">**Benutzerdefinierte Konvertierungen**: Benutzerdefinierte Konvertierungen werden anhand spezieller Methoden durchgeführt, die Sie definieren können, um explizite und implizite Konvertierungen zwischen benutzerdefinierten Typen zu ermöglichen, die nicht in einem Verhältnis „Basisklasse – abgeleitete Klasse“ zueinander stehen.</span><span class="sxs-lookup"><span data-stu-id="7aa81-116">**User-defined conversions**: User-defined conversions are performed by special methods that you can define to enable explicit and implicit conversions between custom types that do not have a base class–derived class relationship.</span></span> <span data-ttu-id="7aa81-117">Weitere Informationen finden Sie unter [Konvertierungsoperatoren](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md).</span><span class="sxs-lookup"><span data-stu-id="7aa81-117">For more information, see [Conversion Operators](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md).</span></span>  
  
-   <span data-ttu-id="7aa81-118">**Konvertierungen mit Hilfsklassen**:Für eine Konvertierung von nicht kompatiblen Typen, z.B. von ganzen Zahlen und <xref:System.DateTime?displayProperty=fullName>-Objekten oder von Hexadezimalzeichenfolgen und Bytearrays, können Sie die <xref:System.BitConverter?displayProperty=fullName>-Klasse, die <xref:System.Convert?displayProperty=fullName>-Klasse und die `Parse`-Methoden der integrierten numerischen Typen (z.B. <xref:System.Int32.Parse%2A?displayProperty=fullName>) verwenden.</span><span class="sxs-lookup"><span data-stu-id="7aa81-118">**Conversions with helper classes**: To convert between non-compatible types, such as integers and <xref:System.DateTime?displayProperty=fullName> objects, or hexadecimal strings and byte arrays, you can use the <xref:System.BitConverter?displayProperty=fullName> class, the <xref:System.Convert?displayProperty=fullName> class, and the `Parse` methods of the built-in numeric types, such as <xref:System.Int32.Parse%2A?displayProperty=fullName>.</span></span> <span data-ttu-id="7aa81-119">Weitere Informationen finden Sie unter [Vorgehensweise: Konvertieren eines Bytearrays in einen ganzzahligen Typ](../../../csharp/programming-guide/types/how-to-convert-a-byte-array-to-an-int.md), [Vorgehensweise: Konvertieren einer Zeichenfolge in eine Zahl](../../../csharp/programming-guide/types/how-to-convert-a-string-to-a-number.md) und [Vorgehensweise: Konvertieren zwischen Hexadezimalzeichenfolgen und numerischen Typen](../../../csharp/programming-guide/types/how-to-convert-between-hexadecimal-strings-and-numeric-types.md).</span><span class="sxs-lookup"><span data-stu-id="7aa81-119">For more information, see [How to: Convert a byte Array to an int](../../../csharp/programming-guide/types/how-to-convert-a-byte-array-to-an-int.md), [How to: Convert a String to a Number](../../../csharp/programming-guide/types/how-to-convert-a-string-to-a-number.md), and [How to: Convert Between Hexadecimal Strings and Numeric Types](../../../csharp/programming-guide/types/how-to-convert-between-hexadecimal-strings-and-numeric-types.md).</span></span>  
  
## <a name="implicit-conversions"></a><span data-ttu-id="7aa81-120">Implizite Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="7aa81-120">Implicit Conversions</span></span>  
 <span data-ttu-id="7aa81-121">Eine implizite Konvertierung kann für integrierte numerische Typen durchgeführt werden, wenn der zu speichernde Wert in die Variable passt, ohne abgeschnitten oder abgerundet zu werden.</span><span class="sxs-lookup"><span data-stu-id="7aa81-121">For built-in numeric types, an implicit conversion can be made when the value to be stored can fit into the variable without being truncated or rounded off.</span></span> <span data-ttu-id="7aa81-122">Eine Variable den Typs [long](../../../csharp/language-reference/keywords/long.md) (8-Byte-Ganzzahl) kann z.B. jeden Wert speichern, den eine Variable des Typs [int](../../../csharp/language-reference/keywords/int.md) (4-Bytes auf einem 32-Bit-Computer) speichern kann.</span><span class="sxs-lookup"><span data-stu-id="7aa81-122">For example, a variable of type [long](../../../csharp/language-reference/keywords/long.md) (8 byte integer) can store any value that an [int](../../../csharp/language-reference/keywords/int.md) (4 bytes on a 32-bit computer) can store.</span></span> <span data-ttu-id="7aa81-123">In folgendem Beispiel konvertiert der Compiler den Wert auf der rechten Seite implizit in einen Typ `long`, bevor er ihn `bigNum` zuweist.</span><span class="sxs-lookup"><span data-stu-id="7aa81-123">In the following example, the compiler implicitly converts the value on the right to a type `long` before assigning it to `bigNum`.</span></span>  
  
 <span data-ttu-id="7aa81-124">[!code-cs[csProgGuideTypes#34](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/casting-and-type-conversions_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="7aa81-124">[!code-cs[csProgGuideTypes#34](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/casting-and-type-conversions_1.cs)]</span></span>  
  
 <span data-ttu-id="7aa81-125">Eine vollständige Liste aller impliziten numerischen Konvertierungen finden Sie unter [Tabelle für implizite numerische Konvertierungen](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="7aa81-125">For a complete list of all implicit numeric conversions, see [Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span></span>  
  
 <span data-ttu-id="7aa81-126">Eine implizite Konvertierungen für Verweistypen von einer Klasse in jede ihrer direkten oder indirekten Basisklassen oder Schnittstellen ist immer möglich.</span><span class="sxs-lookup"><span data-stu-id="7aa81-126">For reference types, an implicit conversion always exists from a class to any one of its direct or indirect base classes or interfaces.</span></span> <span data-ttu-id="7aa81-127">Es ist keine spezielle Syntax erforderlich, da eine abgeleitete Klasse immer alle Member der Basisklasse enthält.</span><span class="sxs-lookup"><span data-stu-id="7aa81-127">No special syntax is necessary because a derived class always contains all the members of a base class.</span></span>  
  
```  
Derived d = new Derived();  
Base b = d; // Always OK.  
```  
  
## <a name="explicit-conversions"></a><span data-ttu-id="7aa81-128">Explizite Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="7aa81-128">Explicit Conversions</span></span>  
 <span data-ttu-id="7aa81-129">Wenn allerdings eine Konvertierung nicht ohne möglichen Informationsverlust durchgeführt werden kann, fordert der Compiler eine explizite Konvertierung; diese wird als *Umwandlung* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="7aa81-129">However, if a conversion cannot be made without a risk of losing information, the compiler requires that you perform an explicit conversion, which is called a *cast*.</span></span> <span data-ttu-id="7aa81-130">Eine Umwandlung bietet die Möglichkeit, den Compiler explizit zu verständigen, dass Sie eine Konvertierung vornehmen möchten, und dass es Ihnen bewusst ist, dass dies einen Datenverlust zur Folge haben kann.</span><span class="sxs-lookup"><span data-stu-id="7aa81-130">A cast is a way of explicitly informing the compiler that you intend to make the conversion and that you are aware that data loss might occur.</span></span> <span data-ttu-id="7aa81-131">Wenn Sie eine Umwandlung durchführen möchten, geben Sie den Typ, in den umgewandelt werden soll, in Klammern am Anfang des zu konvertierenden Wertes oder der zu konvertierenden Variablen an.</span><span class="sxs-lookup"><span data-stu-id="7aa81-131">To perform a cast, specify the type that you are casting to in parentheses in front of the value or variable to be converted.</span></span> <span data-ttu-id="7aa81-132">Das folgende Programm wandelt ein [double](../../../csharp/language-reference/keywords/double.md) in ein [int](../../../csharp/language-reference/keywords/int.md) um.</span><span class="sxs-lookup"><span data-stu-id="7aa81-132">The following program casts a [double](../../../csharp/language-reference/keywords/double.md) to an [int](../../../csharp/language-reference/keywords/int.md).</span></span> <span data-ttu-id="7aa81-133">Das Programm führt ohne die Umwandlung keine Kompilierung durch.</span><span class="sxs-lookup"><span data-stu-id="7aa81-133">The program will not compile without the cast.</span></span>  
  
 <span data-ttu-id="7aa81-134">[!code-cs[csProgGuideTypes#2](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/casting-and-type-conversions_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="7aa81-134">[!code-cs[csProgGuideTypes#2](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/casting-and-type-conversions_2.cs)]</span></span>  
  
 <span data-ttu-id="7aa81-135">Eine Liste der zulässigen expliziten numerischen Konvertierungen finden Sie unter [Tabelle für explizite numerische Konvertierungen](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="7aa81-135">For a list of the explicit numeric conversions that are allowed, see [Explicit Numeric Conversions Table](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md).</span></span>  
  
 <span data-ttu-id="7aa81-136">Eine explizite Umwandlung ist für Verweistypen erforderlich, wenn Sie von einer Basisklasse in eine abgeleitete Klasse konvertieren möchten:</span><span class="sxs-lookup"><span data-stu-id="7aa81-136">For reference types, an explicit cast is required if you need to convert from a base type to a derived type:</span></span>  
  
```csharp  
// Create a new derived type.  
Giraffe g = new Giraffe();  
  
// Implicit conversion to base type is safe.  
Animal a = g;  
  
// Explicit conversion is required to cast back  
// to derived type. Note: This will compile but will  
// throw an exception at run time if the right-side  
// object is not in fact a Giraffe.  
Giraffe g2 = (Giraffe) a;  
```  
  
 <span data-ttu-id="7aa81-137">Ein Umwandlungsvorgang zwischen Verweistypen ändert nicht den Laufzeittypen des zugrunde liegenden Objekts; er ändert lediglich den Typ des Wertes, der als Verweis auf das Objekt verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7aa81-137">A cast operation between reference types does not change the run-time type of the underlying object; it only changes the type of the value that is being used as a reference to that object.</span></span> <span data-ttu-id="7aa81-138">Weitere Informationen finden Sie unter [Polymorphie](../../../csharp/programming-guide/classes-and-structs/polymorphism.md).</span><span class="sxs-lookup"><span data-stu-id="7aa81-138">For more information, see [Polymorphism](../../../csharp/programming-guide/classes-and-structs/polymorphism.md).</span></span>  
  
## <a name="type-conversion-exceptions-at-run-time"></a><span data-ttu-id="7aa81-139">Typkonvertierungsausnahmen zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="7aa81-139">Type Conversion Exceptions at Run Time</span></span>  
 <span data-ttu-id="7aa81-140">In manchen Verweistypkonvertierungen kann der Compiler nicht bestimmen, ob eine Umwandlung zulässig wäre.</span><span class="sxs-lookup"><span data-stu-id="7aa81-140">In some reference type conversions, the compiler cannot determine whether a cast will be valid.</span></span> <span data-ttu-id="7aa81-141">Es ist möglich, dass ein Umwandlungsvorgang, der ordnungsgemäß kompiliert, zur Laufzeit fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="7aa81-141">It is possible for a cast operation that compiles correctly to fail at run time.</span></span> <span data-ttu-id="7aa81-142">Eine fehlgeschlagene Typumwandlung zur Laufzeit löst wie in folgendem Beispiel dargestellt eine <xref:System.InvalidCastException> aus.</span><span class="sxs-lookup"><span data-stu-id="7aa81-142">As shown in the following example, a type cast that fails at run time will cause an <xref:System.InvalidCastException> to be thrown.</span></span>  
  
 <span data-ttu-id="7aa81-143">[!code-cs[csProgGuideTypes#41](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/casting-and-type-conversions_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="7aa81-143">[!code-cs[csProgGuideTypes#41](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/casting-and-type-conversions_3.cs)]</span></span>  
  
 <span data-ttu-id="7aa81-144">C# stellt die Operatoren [is](../../../csharp/language-reference/keywords/is.md) und [as](../../../csharp/language-reference/keywords/as.md) bereit, mit denen Sie vor einer Umwandlung auf Kompatibilität prüfen können.</span><span class="sxs-lookup"><span data-stu-id="7aa81-144">C# provides the [is](../../../csharp/language-reference/keywords/is.md) and [as](../../../csharp/language-reference/keywords/as.md) operators to enable you to test for compatibility before actually performing a cast.</span></span> <span data-ttu-id="7aa81-145">Weitere Informationen finden Sie unter [Vorgehensweise: Sichere Umwandlung mit den Operatoren „as“ und „is“](../../../csharp/programming-guide/types/how-to-safely-cast-by-using-as-and-is-operators.md).</span><span class="sxs-lookup"><span data-stu-id="7aa81-145">For more information, see [How to: Safely Cast by Using as and is Operators](../../../csharp/programming-guide/types/how-to-safely-cast-by-using-as-and-is-operators.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="7aa81-146">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="7aa81-146">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  

## <a name="see-also"></a><span data-ttu-id="7aa81-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7aa81-147">See Also</span></span>  
 <span data-ttu-id="7aa81-148">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="7aa81-148">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="7aa81-149">[Typen](../../../csharp/programming-guide/types/index.md) </span><span class="sxs-lookup"><span data-stu-id="7aa81-149">[Types](../../../csharp/programming-guide/types/index.md) </span></span>  
 <span data-ttu-id="7aa81-150">[()-Operator](../../../csharp/language-reference/operators/invocation-operator.md) </span><span class="sxs-lookup"><span data-stu-id="7aa81-150">[() Operator](../../../csharp/language-reference/operators/invocation-operator.md) </span></span>  
 <span data-ttu-id="7aa81-151">[explicit](../../../csharp/language-reference/keywords/explicit.md) </span><span class="sxs-lookup"><span data-stu-id="7aa81-151">[explicit](../../../csharp/language-reference/keywords/explicit.md) </span></span>  
 <span data-ttu-id="7aa81-152">[implicit](../../../csharp/language-reference/keywords/implicit.md) </span><span class="sxs-lookup"><span data-stu-id="7aa81-152">[implicit](../../../csharp/language-reference/keywords/implicit.md) </span></span>  
 <span data-ttu-id="7aa81-153">[Konvertierungsoperatoren](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md) </span><span class="sxs-lookup"><span data-stu-id="7aa81-153">[Conversion Operators](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md) </span></span>  
 <span data-ttu-id="7aa81-154">[Verallgemeinerte Typkonvertierung](http://msdn.microsoft.com/library/49253ae6-7657-4810-82ab-1176a6feeada) </span><span class="sxs-lookup"><span data-stu-id="7aa81-154">[Generalized Type Conversion](http://msdn.microsoft.com/library/49253ae6-7657-4810-82ab-1176a6feeada) </span></span>  
 <span data-ttu-id="7aa81-155">[Konvertieren exportierter Typen](http://msdn.microsoft.com/en-us/1dfe55f4-07a2-4b61-aabf-a8cf65783a6b) </span><span class="sxs-lookup"><span data-stu-id="7aa81-155">[Exported Type Conversion](http://msdn.microsoft.com/en-us/1dfe55f4-07a2-4b61-aabf-a8cf65783a6b) </span></span>  
 [<span data-ttu-id="7aa81-156">Gewusst wie: Konvertieren einer Zeichenfolge in eine Zahl</span><span class="sxs-lookup"><span data-stu-id="7aa81-156">How to: Convert a String to a Number</span></span>](../../../csharp/programming-guide/types/how-to-convert-a-string-to-a-number.md)


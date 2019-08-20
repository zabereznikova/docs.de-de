---
title: 'Operator „::“: C#-Referenz'
ms.custom: seodec18
ms.date: 08/09/2019
f1_keywords:
- ::_CSharpKeyword
- global_CSharpKeyword
helpviewer_keywords:
- ':: operator [C#]'
- namespace alias qualifier [C#]
- namespace [C#]
- global keyword [C#]
ms.assetid: 698b5a73-85cf-4e0e-9e8e-6496887f8527
ms.openlocfilehash: 2aceb51747708b12fb3059b097b72206c78a9d5d
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/13/2019
ms.locfileid: "68971241"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="b1540-102">Operator „::“ (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="b1540-102">:: operator (C# reference)</span></span>

<span data-ttu-id="b1540-103">Verwenden Sie den Namespacealias-Qualifizierer `::`, um auf die Member eines Namespace mit Alias zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="b1540-103">Use the namespace alias qualifier `::` to access members of an aliased namespace.</span></span> <span data-ttu-id="b1540-104">Sie verwenden den `::`-Qualifizierer zwischen zwei Bezeichnern.</span><span class="sxs-lookup"><span data-stu-id="b1540-104">You use the `::` qualifier between two identifiers.</span></span> <span data-ttu-id="b1540-105">Der linke Bezeichner kann einer der folgenden Aliase sein:</span><span class="sxs-lookup"><span data-stu-id="b1540-105">The left-hand identifier can be any of the following aliases:</span></span>

- <span data-ttu-id="b1540-106">Ein mit der [using alias-Anweisung](../keywords/using-directive.md)erstellter Namespacealias:</span><span class="sxs-lookup"><span data-stu-id="b1540-106">A namespace alias created with the [using alias directive](../keywords/using-directive.md):</span></span>
  
  ```csharp
  using forwinforms = System.Drawing;
  using forwpf = System.Windows;
  
  public class Converters
  {
      public static forwpf::Point Convert(forwinforms::Point point) => new forwpf::Point(point.X, point.Y);
  }
  ```

- <span data-ttu-id="b1540-107">Ein [externer Alias](../keywords/extern-alias.md).</span><span class="sxs-lookup"><span data-stu-id="b1540-107">An [extern alias](../keywords/extern-alias.md).</span></span>
- <span data-ttu-id="b1540-108">Der `global`-Alias, ein globaler Namespacealias.</span><span class="sxs-lookup"><span data-stu-id="b1540-108">The `global` alias, which is the global namespace alias.</span></span> <span data-ttu-id="b1540-109">Der globale Namespace ist der Namespace, der Namespaces und Typen enthält, die nicht in einem benannten Namespace deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="b1540-109">The global namespace is the namespace that contains namespaces and types that are not declared inside a named namespace.</span></span> <span data-ttu-id="b1540-110">Bei Verwendung mit dem `::`-Qualifizierer verweist der `global`-Alias immer auf den globalen Namespace, auch wenn ein benutzerdefinierter `global` Namespacealias vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="b1540-110">When used with the `::` qualifier, the `global` alias always references the global namespace, even if there is the user-defined `global` namespace alias.</span></span>
  
  <span data-ttu-id="b1540-111">Im folgenden Beispiel wird der `global`-Alias verwendet, um auf den .NET-Namespace <xref:System> zuzugreifen, der ein Member des globalen Namespace ist.</span><span class="sxs-lookup"><span data-stu-id="b1540-111">The following example uses the `global` alias to access the .NET <xref:System> namespace, which is a member of the global namespace.</span></span> <span data-ttu-id="b1540-112">Ohne den `global`-Alias würde auf den benutzerdefinierten `System`-Namespace, der ein Member des `MyCompany.MyProduct`-Namespace ist, zugegriffen:</span><span class="sxs-lookup"><span data-stu-id="b1540-112">Without the `global` alias, the user-defined `System` namespace, which is a member of the `MyCompany.MyProduct` namespace, would be accessed:</span></span>

  ```csharp
  namespace MyCompany.MyProduct.System
  {
      class Program
      {
          static void Main() => global::System.Console.WriteLine("Using global alias");
      }
  
      class Console
      {
          string Suggestion => "Consider renaming this class";
      }
  }
  ```
  
  > [!NOTE]
  > <span data-ttu-id="b1540-113">Das Schlüsselwort `global` ist nur dann der globale Namespacealias, wenn es sich um den linken Bezeichner des `::`-Qualifizierers handelt.</span><span class="sxs-lookup"><span data-stu-id="b1540-113">The `global` keyword is the global namespace alias only when it's the left-hand identifier of the `::` qualifier.</span></span>

<span data-ttu-id="b1540-114">Sie können auch den [member access`.`-Operator](member-access-operators.md#member-access-operator-) verwenden, um auf Member eines Namespace mit Alias zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="b1540-114">You can also use the [member access `.` operator](member-access-operators.md#member-access-operator-) to access members of an aliased namespace.</span></span> <span data-ttu-id="b1540-115">Allerdings wird der `.`-Operator auch verwendet, um auf Member eines Typs zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="b1540-115">However, the `.` operator is also used to access members of a type.</span></span> <span data-ttu-id="b1540-116">Der Qualifizierer `::` stellt sicher, dass sein linker Bezeichner immer auf einen Namespacealias verweist, selbst wenn ein Typ oder ein Namespace mit demselben Namen vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="b1540-116">The `::` qualifier ensures that its left-hand identifier always references a namespace alias, even if there exists a type or namespace with the same name.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="b1540-117">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="b1540-117">C# language specification</span></span>

<span data-ttu-id="b1540-118">Weitere Informationen finden Sie im Abschnitt [Namespacealias-Qualifizierer](~/_csharplang/spec/namespaces.md#namespace-alias-qualifiers) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="b1540-118">For more information, see the [Namespace alias qualifiers](~/_csharplang/spec/namespaces.md#namespace-alias-qualifiers) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b1540-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b1540-119">See also</span></span>

- [<span data-ttu-id="b1540-120">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="b1540-120">C# reference</span></span>](../index.md)
- [<span data-ttu-id="b1540-121">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="b1540-121">C# operators</span></span>](index.md)
- [<span data-ttu-id="b1540-122">Verwenden von Namespaces</span><span class="sxs-lookup"><span data-stu-id="b1540-122">Using namespaces</span></span>](../../programming-guide/namespaces/using-namespaces.md)

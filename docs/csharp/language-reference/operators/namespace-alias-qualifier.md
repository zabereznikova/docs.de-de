---
title: 'Operator „::“: C#-Referenz'
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
ms.openlocfilehash: a18e52ea05d49bf2b3a468923f1433f09fff9a8b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "75712675"
---
# <a name="-operator-c-reference"></a>Operator „::“ (C#-Referenz)

Verwenden Sie den Namespacealias-Qualifizierer `::`, um auf einen Member eines Namespace mit Alias zuzugreifen. Sie können den `::`-Qualifizierer nur zwischen zwei Bezeichnern verwenden. Der linke Bezeichner kann einer der folgenden Aliase sein:

- Ein mit einer [using alias-Anweisung](../keywords/using-directive.md) erstellter Namespacealias:

  ```csharp
  using forwinforms = System.Drawing;
  using forwpf = System.Windows;
  
  public class Converters
  {
      public static forwpf::Point Convert(forwinforms::Point point) => new forwpf::Point(point.X, point.Y);
  }
  ```

- Ein [externer Alias](../keywords/extern-alias.md).
- Der `global`-Alias, ein globaler Namespacealias. Der globale Namespace ist der Namespace, der Namespaces und Typen enthält, die nicht in einem benannten Namespace deklariert werden. Bei Verwendung mit dem `::`-Qualifizierer verweist der `global`-Alias immer auf den globalen Namespace, auch wenn ein benutzerdefinierter `global` Namespacealias vorhanden ist.

  Im folgenden Beispiel wird der `global`-Alias verwendet, um auf den .NET-Namespace <xref:System> zuzugreifen, der ein Member des globalen Namespace ist. Ohne den `global`-Alias würde auf den benutzerdefinierten `System`-Namespace, der ein Member des `MyCompany.MyProduct`-Namespace ist, zugegriffen:

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
  > Das Schlüsselwort `global` ist nur dann der globale Namespacealias, wenn es sich um den linken Bezeichner des `::`-Qualifizierers handelt.

Sie können auch den [member access`.`-Operator ](member-access-operators.md#member-access-operator-) verwenden, um auf einen Member eines Namespace mit Alias zuzugreifen. Allerdings wird der `.`-Operator auch verwendet, um auf einen Typmember zuzugreifen. Der Qualifizierer `::` stellt sicher, dass sein linker Bezeichner immer auf einen Namespacealias verweist, selbst wenn ein Typ oder ein Namespace mit demselben Namen vorhanden ist.

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie im Abschnitt [Namespacealias-Qualifizierer](~/_csharplang/spec/namespaces.md#namespace-alias-qualifiers) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Weitere Informationen

- [C#-Referenz](../index.md)
- [C#-Operatoren](index.md)
- [Verwenden von Namespaces](../../programming-guide/namespaces/using-namespaces.md)

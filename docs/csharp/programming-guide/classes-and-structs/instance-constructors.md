---
title: Instanzkonstruktoren – C#-Programmierhandbuch
description: Instanzkonstruktoren in C# erstellen und initialisieren Instanzmembervariablen, wenn Sie den neuen Ausdruck verwenden, um ein Objekt einer Klasse zu erstellen.
ms.date: 07/20/2015
helpviewer_keywords:
- constructors [C#], instance constructors
- instance constructors [C#]
ms.assetid: 24663779-c1e5-4af4-a942-ca554e4c542d
ms.openlocfilehash: d70e786446fb198afb4e0311757cacb65b706f47
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/21/2020
ms.locfileid: "86864201"
---
# <a name="instance-constructors-c-programming-guide"></a>Instanzkonstruktoren (C#-Programmierhandbuch)

Instanzkonstruktoren werden zum Erstellen und Initialisieren von Instanzmembervariablen verwendet, wenn Sie die Ausdruck [new](../../language-reference/operators/new-operator.md) verwenden, um ein Objekt einer [Klasse](../../language-reference/keywords/class.md) zu erstellen. Sie müssen einen statischen Konstruktor definieren um eine [statische](../../language-reference/keywords/static.md) Klasse oder eine statische Variable in einer nicht statischen Klasse zu initialisieren. Weitere Informationen finden Sie unter [Statische Konstruktoren](./static-constructors.md).  
  
 Im folgenden Beispiel wird die Verwendung eines Instanzkonstruktors veranschaulicht:  
  
 [!code-csharp[csProgGuideObjects#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#5)]  
  
> [!NOTE]
> Der Deutlichkeit halber enthält diese Klasse öffentliche Felder. Das Verwenden von öffentlichen Felder wird beim Programmieren nicht empfohlen, da so jede Methode im Programm uneingeschränkten und ungeprüften Zugriff auf das Innenleben eines Objekts erhält. Datenmember sollten im Allgemeinen privat sein. Außerdem sollte auf sie nur über Klassenmethoden und Eigenschaften zugegriffen werden.  
  
 Dieser Instanzkonstruktor wird aufgerufen, wenn ein Objekt basierend auf der `Coords`-Klasse erstellt wird. Ein derartiger Konstruktor, der keine Argumente akzeptiert, wird als *parameterloser Konstruktor* bezeichnet. Es kann jedoch oft hilfreich sein, weitere Konstruktoren bereitzustellen. Sie können beispielsweise einen Konstruktor in die `Coords`-Klasse einfügen, mit dem Sie die Anfangswerte der Datenmember angeben können:  
  
 [!code-csharp[csProgGuideObjects#76](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#76)]  
  
 Damit können `Coords`-Objekte mit Standard- oder spezifischen Anfangswerten erstellt werden. Dies geschieht wie folgt:  
  
 [!code-csharp[csProgGuideObjects#77](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#77)]  
  
 Wenn eine Klasse über keinen Konstruktor verfügt, wird automatisch ein parameterloser Konstruktor generiert, und die Objektfelder werden mit Standardwerte initialisiert. Ein [int](../../language-reference/builtin-types/integral-numeric-types.md)-Objekt wird beispielsweise auf 0 (null) initialisiert. Informationen zu den Typstandardwerten finden Sie unter [Standardwerte der C#-Typen](../../language-reference/builtin-types/default-values.md). Da der parameterloser Konstruktor der `Coords`-Klasse alle Datenmember auf 0 (null) initialisiert, kann er komplett entfernt werden, ohne dass die Arbeitsweise der Klasse geändert wird. Unter Beispiel 1 weiter unten in diesem Thema finden Sie ein vollständiges Beispiel mit mehreren Konstruktoren. Unter Beispiel 2 finden Sie ein Beispiel für einen automatisch generierten Konstruktor.  
  
 Instanzkonstruktoren können ebenfalls dazu verwendet werden, die Instanzkonstruktoren von Basisklassen aufzurufen. Der Klassenkonstruktor kann den Konstruktor der Basisklasse mit dem Initialisierer wie folgt aufrufen:  
  
 [!code-csharp[csProgGuideObjects#78](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#78)]  
  
 In diesem Beispiel übergibt die `Circle`-Klasse die Werte des Radius und der Höhe an den Konstruktor, der von `Shape` bereitgestellt wird, von dem `Circle` abgeleitet wird. Unter Beispiel 3 in diesem Thema finden Sie ein vollständiges Beispiel mit `Shape` und `Circle`.  
  
## <a name="example-1"></a>Beispiel 1  
 Das folgende Beispiel veranschaulicht eine Klasse mit zwei Klassenkonstruktoren. Einer der Konstruktoren hat kein Argument und der andere verfügt über zwei.  
  
 [!code-csharp[csProgGuideObjects#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#4)]  
  
## <a name="example-2"></a>Beispiel 2  
 In diesem Beispiel hat die `Person`-Klasse keine Konstruktoren. In einem solchen Fall wird automatisch ein parameterloser Konstruktor bereitgestellt, und die Felder werden auf ihre Standardwerte initialisiert.  
  
 [!code-csharp[csProgGuideObjects#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#8)]  
  
 Beachten Sie, dass der Standardwert von `age``0` ist, und der Standardwert von `name` ist `null`.
  
## <a name="example-3"></a>Beispiel 3  
 Im folgenden Beispiel wird die Verwendung vom Basisklasseninitialisierer veranschaulicht. Die `Circle`-Klasse wird von der allgemeinen Klasse `Shape` abgeleitet, und die `Cylinder`-Klasse wird von der `Circle`-Klasse abgeleitet. Der Konstruktor von jeder abgeleiteten Klasse verwendet deren Basisklasseninitialisierer.  
  
 [!code-csharp[csProgGuideObjects#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#9)]  
  
 Weitere Beispiele für das Aufrufen des Basisklassenkonstruktors finden Sie unter [virtual](../../language-reference/keywords/virtual.md), [override](../../language-reference/keywords/override.md) und [base](../../language-reference/keywords/base.md).  
  
## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../index.md)
- [Klassen und Strukturen](./index.md)
- [Konstruktoren](./constructors.md)
- [Finalizer](./destructors.md)
- [static](../../language-reference/keywords/static.md)

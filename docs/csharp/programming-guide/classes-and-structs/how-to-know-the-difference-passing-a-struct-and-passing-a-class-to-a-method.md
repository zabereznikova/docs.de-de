---
title: 'Gewusst wie: Unterschiede zwischen dem Übergeben einer Struktur und dem Übergeben eines Klassenverweises an eine Methode – C#-Programmierhandbuch'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- structs [C#], passing as method parameter
- passing parameters [C#], structs vs. classes
- methods [C#], passing classes vs. structs
ms.assetid: 9c1313a6-32a8-4ea7-a59f-450f66af628b
ms.openlocfilehash: 9bacc7b3913a6e353e39f1e45fa99ea2dcdbe668
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73970545"
---
# <a name="how-to-know-the-difference-between-passing-a-struct-and-passing-a-class-reference-to-a-method-c-programming-guide"></a>Gewusst wie: Unterschiede zwischen dem Übergeben einer Struktur und dem Übergeben eines Klassenverweises an eine Methode (C#-Programmierhandbuch)
Das folgende Beispiel stellt dar, wie die Übergabe einer [Struktur](../../language-reference/keywords/struct.md) an eine Methode sich von der Übergabe einer [Klasseninstanz](../../language-reference/keywords/class.md) an eine Methode unterscheidet. Im Beispiel werden beide Argumente (Struktur und Klasseninstanz) nach Wert übergeben, und beide Methoden ändern den Wert eines Felds des Arguments. Allerdings sind die Ergebnisse der beiden Methoden nicht identisch, denn wenn Sie eine Struktur übergeben, unterscheidet sich dies von dem, wenn Sie eine Instanz einer Klasse übergeben.  
  
 Da eine Struktur ein [Werttyp](../../language-reference/keywords/value-types.md) ist, wenn Sie [eine Struktur nach Wert](./passing-value-type-parameters.md) an eine Methode übergeben, erhält und funktioniert die Methode nur mit einer Kopie des Strukturarguments. Die Methode hat keinen Zugriff auf die ursprüngliche Struktur in der aufrufenden Methode und kann sie deshalb nicht ändern. Die Methode kann nur die Kopie ändern.  
  
 Eine Instanz der Klasse ist ein [Verweistyp](../../language-reference/keywords/reference-types.md), kein Werttyp. Wenn [ein Verweistyp als Wert](./passing-reference-type-parameters.md) an eine Methode übergeben wird, erhält die Methode eine Kopie des Verweises auf die Klasseninstanz. Die aufgerufene Methode erhält also eine Kopie der Adresse der Instanz, während die aufrufende Methode die ursprüngliche Adresse der Instanz beibehält. Die Klasseninstanz in der aufrufenden Methode verfügt über eine Adresse, der Parameter in der aufgerufenen Methode verfügt über eine Kopie der Adresse und beide Adressen verweisen auf dasselbe Objekt. Da der Parameter nur eine Kopie der Adresse enthält, kann die aufgerufene Methode nicht die Adresse der Klasseninstanz in der aufrufenden Methode ändern. Allerdings kann die aufgerufene Methode die Kopie der Adresse verwenden, um auf die Klassenmember zuzugreifen, auf die die ursprüngliche Adresse und die Kopie der Adresse verweisen. Wenn die aufgerufene Methode einen Klassenmember ändert, ändert sich auch die ursprüngliche Klasseninstanz in der aufrufenden Methode.  
  
 Die Ausgabe des folgenden Beispiels veranschaulicht den Unterschied. Der Wert des Felds `willIChange` der Klasseninstanz wird durch den Aufruf auf die Methode `ClassTaker` geändert, da die Methode die Adresse im Parameter verwendet, um das angegebene Feld der Klasseninstanz zu finden. Das Feld `willIChange` der Struktur in der aufrufenden Methode wird nicht durch den Aufruf auf die Methode `StructTaker` geändert, da der Wert des Arguments eine Kopie der Struktur selbst ist und keine Kopie deren Adresse. `StructTaker` ändert die Kopie, und die Kopie wird abgebrochen, wenn der Aufruf auf `StructTaker` abgeschlossen ist.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[csProgGuideObjects#32](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#32)]  
  
## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../index.md)
- [Klassen](./classes.md)
- [Strukturen](./structs.md)
- [Übergeben von Parametern](./passing-parameters.md)

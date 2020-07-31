---
title: Private Konstruktoren – C#-Programmierhandbuch
description: Ein privater Konstruktor ist ein spezieller Instanzkonstruktor in C#, der verwendet wird, um einzuschränken, wie ein Objekt erstellt werden kann. Sie können mit Factorymethoden oder anderen Konstruktionsausdrücken verwendet werden.
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, private constructors
- private constructors [C#]
ms.assetid: 29eeaa7d-8d81-453c-94b9-0e2800172621
ms.openlocfilehash: a6b86ccb870da0262bcbc516e176e00d17724f9f
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/21/2020
ms.locfileid: "86864058"
---
# <a name="private-constructors-c-programming-guide"></a>Private Konstruktoren (C#-Programmierhandbuch)
Ein privater Konstruktor ist ein spezieller Instanzenkonstruktor. Er wird im Allgemeinen in Klassen verwenden, die nur statische Member enthalten. Wenn eine Klasse einen oder mehrere private und keine öffentlichen Konstruktoren besitzt, können andere Klassen (außer geschachtelte Klassen) keine Instanzen dieser Klasse erstellen. Zum Beispiel:  
  
 [!code-csharp[csProgGuideObjects#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#11)]  
  
 Die Deklaration des leeren Konstruktors verhindert die automatische Erstellung eines parameterlosen Konstruktors. Beachten Sie, dass wenn Sie keinen Zugriffsmodifizierer mit dem Konstruktor verwenden, der Konstruktor standardmäßig weiterhin privat ist. Allerdings werden die [privaten](../../language-reference/keywords/private.md) Modifizierer normalerweise ausdrücklich verwendet, um klarzustellen, dass die Klasse nicht instanziiert werden kann.  
  
 Private Konstruktoren werden verwendet, um das Erstellen von Instanzen einer Klasse zu verhindern, wenn es keine Instanzfelder oder -methoden wie die <xref:System.Math>-Klasse gibt oder wenn eine Methode aufgerufen wird, um eine Instanz einer Klasse abzurufen. Wenn alle Methoden in der Klasse statisch sind, erwägen Sie es, die komplette Klasse statisch zu machen. Weitere Informationen finden Sie unter [Statische Klassen und statische Klassenmember](./static-classes-and-static-class-members.md).  
  
## <a name="example"></a>Beispiel  
 Folgendes ist ein Beispiel einer Klasse, die einen privaten Konstruktor verwendet.  
  
 [!code-csharp[csProgGuideObjects#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#12)]  
  
 Beachten Sie, dass wenn Sie die Auskommentierung der folgenden Anweisung aus dem Beispiel aufheben, ein Fehler erzeugt wird, weil auf den Konstruktor aufgrund seiner Schutzebene nicht zugegriffen werden kann:  
  
 [!code-csharp[csProgGuideObjects#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#13)]  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  

Weitere Informationen erhalten Sie unter [Private Konstruktoren](~/_csharplang/spec/classes.md#private-constructors) in der [C#-Sprachspezifikation](/dotnet/csharp/language-reference/language-specification/introduction). Die Sprachspezifikation ist die verbindliche Quelle für die Syntax und Verwendung von C#.
  
## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../index.md)
- [Klassen und Strukturen](./index.md)
- [Konstruktoren](./constructors.md)
- [Finalizer](./destructors.md)
- [private](../../language-reference/keywords/private.md)
- [public](../../language-reference/keywords/public.md)

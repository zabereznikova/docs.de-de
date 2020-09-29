---
title: 'Gewusst wie: Erstellen einer neuen Methode für eine Enumeration – C#-Programmierhandbuch'
description: Informationen zur Verwendung von Erweiterungsmethoden zum Hinzuzufügen von Funktionen zu einer Enumeration in C# Dieses Beispiel zeigt eine Erweiterungsmethode mit dem Namen „Passing“ für eine Aufzählung namens „Grades“.
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [C#]
- extension methods [C#], for enums
- enum extensibility [C#]
ms.assetid: 100106f9-1e54-462c-8ebe-3892fe23b6eb
ms.openlocfilehash: 2714b29d64e18250f0fe379aee1c09c242d3f63f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91174263"
---
# <a name="how-to-create-a-new-method-for-an-enumeration-c-programming-guide"></a>Gewusst wie: Erstellen einer neuen Methode für eine Enumeration (C#-Programmierhandbuch)

Sie können Erweiterungsmethoden verwenden, um für einen bestimmten Enumerationstyp spezifische Funktionen hinzuzufügen.  
  
## <a name="example"></a>Beispiel  

 Im folgenden Beispiel stellt die `Grades`-Enumeration die möglichen Noten in Buchstaben dar, die ein Schüler im Unterricht erhalten kann. Eine Erweiterungsmethode mit dem Namen `Passing` wird dem `Grades`-Typ hinzugefügt, sodass jede Instanz dieses Typs nun „weiß“, ob sie eine Note darstellt, mit der der Schüler bestanden hat.  
  
 [!code-csharp[csProgGuideExtensionMethods#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExtensionMethods/cs/extensionmethods.cs#2)]  
  
 Beachten Sie, dass die `Extensions`-Klasse auch eine statische Variable enthält, die dynamisch aktualisiert wird, und dass der Rückgabewert der Erweiterungsmethode den aktuellen Wert der Variablen darstellt. Dies zeigt, dass hinter den Kulissen Erweiterungsmethoden direkt auf der statischen Klasse aufgerufen werden, in der sie definiert sind.  
  
## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../index.md)
- [Erweiterungsmethoden](./extension-methods.md)

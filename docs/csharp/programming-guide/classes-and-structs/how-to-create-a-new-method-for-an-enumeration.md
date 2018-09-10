---
title: 'Gewusst wie: Erstellen einer neuen Methode für eine Enumeration (C#-Programmierhandbuch)'
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [C#]
- extension methods [C#], for enums
- enum extensibility [C#]
ms.assetid: 100106f9-1e54-462c-8ebe-3892fe23b6eb
ms.openlocfilehash: 3e153dbbe80ed850705ddaea4a9a3d5aba570fe0
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43508946"
---
# <a name="how-to-create-a-new-method-for-an-enumeration-c-programming-guide"></a>Gewusst wie: Erstellen einer neuen Methode für eine Enumeration (C#-Programmierhandbuch)
Sie können Erweiterungsmethoden verwenden, um für einen bestimmten Enumerationstyp spezifische Funktionen hinzuzufügen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel stellt die `Grades`-Enumeration die möglichen Noten in Buchstaben dar, die ein Schüler im Unterricht erhalten kann. Eine Erweiterungsmethode mit dem Namen `Passing` wird dem `Grades`-Typ hinzugefügt, sodass jede Instanz dieses Typs nun „weiß“, ob sie eine Note darstellt, mit der der Schüler bestanden hat.  
  
 [!code-csharp[csProgGuideExtensionMethods#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-create-a-new-method-for-an-enumeration_1.cs)]  
  
 Beachten Sie, dass die `Extensions`-Klasse auch eine statische Variable enthält, die dynamisch aktualisiert wird, und dass der Rückgabewert der Erweiterungsmethode den aktuellen Wert der Variablen darstellt. Dies zeigt, dass hinter den Kulissen Erweiterungsmethoden direkt auf der statischen Klasse aufgerufen werden, in der sie definiert sind.  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Kopieren Sie diesen Code, und fügen Sie ihn in ein Visual C#-Konsolenanwendungsprojekt ein, das in Visual Studio erstellt wurde, um den Code auszuführen. Standardmäßig wird dieses Projekt mit Version 3.5 von [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] verwendet und verfügt über einen Verweis auf „System.Core.dll“ und eine `using`-Anweisung für „System.Linq“. Wenn eine oder mehrere dieser Anforderungen im Projekt nicht vorhanden sind, können Sie sie manuell hinzufügen.  
  
## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
- [Erweiterungsmethoden](../../../csharp/programming-guide/classes-and-structs/extension-methods.md)

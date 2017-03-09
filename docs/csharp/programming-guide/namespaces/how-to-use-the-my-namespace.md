---
title: "Gewusst wie: Verwenden des My-Namespaces (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "C#-Sprache, Zugriff auf eigenen Namespace"
ms.assetid: e7152414-0ea5-4c8e-bf02-c8d5bbe45ff4
caps.latest.revision: 12
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 12
---
# Gewusst wie: Verwenden des My-Namespaces (C#-Programmierhandbuch)
Der <xref:Microsoft.VisualBasic.MyServices>\-Namespace \(`My` in Visual Basic\) bietet einen einfachen und intuitiven Zugriff auf eine Reihe von .NET Framework\-Klassen. Mit diesem Namespace können Sie Code schreiben, der mit dem Computer, der Anwendung sowie mit Einstellungen, Ressourcen usw. interagiert.  Obwohl der `MyServices`\-Namespace ursprünglich für die Verwendung in Visual Basic entwickelt wurde, kann er auch in C\#\-Anwendungen verwendet werden.  
  
 Weitere Informationen zum Verwenden des `MyServices`\-Namespaces aus Visual Basic finden Sie unter [Development with My](../../../visual-basic/developing-apps/development-with-my/index.md).  
  
## Hinzufügen eines Verweises  
 Bevor Sie die `MyServices`\-Klassen in einer Projektmappe verwenden können, müssen Sie einen Verweis auf die Visual Basic\-Bibliothek hinzufügen.  
  
#### Hinzufügen eines Verweises auf die Visual Basic\-Bibliothek  
  
1.  Klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf den Knoten **Verweise**, und wählen Sie dann **Verweis hinzufügen** aus.  
  
2.  Das Dialogfeld **Verweise** wird angezeigt. Führen Sie in der Liste einen Bildlauf nach unten durch, und wählen Sie Microsoft.VisualBasic.dll aus.  
  
     Sie haben auch die Möglichkeit, dem `using`\-Abschnitt am Anfang des Programms die folgende Zeile hinzuzufügen.  
  
     [!code-cs[csProgGuideNamespaces#18](../../../csharp/programming-guide/namespaces/codesnippet/csharp/Namespaces/Namespaces3.cs#18)]  
  
## Beispiel  
 Dieses Beispiel ruft verschiedene im `MyServices`\-Namespace enthaltene statische Methoden auf.  Damit dieser Code kompiliert wird, muss dem Projekt ein Verweis auf Microsoft.VisualBasic.DLL hinzugefügt werden.  
  
 [!code-cs[csProgGuideNamespaces#19](../../../csharp/programming-guide/namespaces/codesnippet/csharp/Namespaces/Namespaces3.cs#19)]  
  
 Nicht alle Klassen im `MyServices`\-Namespace können von einer C\#\-Anwendung aufgerufen werden. Die <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy>\-Klasse ist beispielsweise nicht kompatibel.  In diesem speziellen Fall können stattdessen die statischen Methoden verwendet werden, die Teil von <xref:Microsoft.VisualBasic.FileIO.FileSystem> sind und auch in VisualBasic.dll enthalten sind.  Das folgende Beispiel zeigt, wie ein Verzeichnis mit einer solchen Methode dupliziert werden kann:  
  
 [!code-cs[csProgGuideNamespaces#20](../../../csharp/programming-guide/namespaces/codesnippet/csharp/Namespaces/Namespaces3.cs#20)]  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Namespaces](../../../csharp/programming-guide/namespaces/index.md)   
 [Verwenden von Namespaces](../../../csharp/programming-guide/namespaces/using-namespaces.md)
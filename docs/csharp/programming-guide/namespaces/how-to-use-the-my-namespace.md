---
title: 'Gewusst wie: Verwenden des My-Namespaces (C#-Programmierhandbuch)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: C# language, My namespace access
ms.assetid: e7152414-0ea5-4c8e-bf02-c8d5bbe45ff4
caps.latest.revision: "12"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: f3564c594a5fbb9bd05a956e5c12bbb173d2db51
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-the-my-namespace-c-programming-guide"></a>Gewusst wie: Verwenden des My-Namespaces (C#-Programmierhandbuch)
Der <xref:Microsoft.VisualBasic.MyServices>-Namespace (`My` in Visual Basic) bietet einfachen und intuitiven Zugriff auf mehrere .NET Framework-Klassen, mit denen Sie Code schreiben können, der mit dem Computer, der Anwendung, den Einstellungen, den Ressourcen usw. interagiert. Auch wenn er ursprünglich für Visual Basic entwickelt wurde, kann der `MyServices`-Namespace auch in C#-Anwendungen verwendet werden.  
  
 Weitere Informationen zum Verwenden des `MyServices`-Namespace in Visual Basic finden Sie unter [Development with My (Entwicklung mit „My“)](../../../visual-basic/developing-apps/development-with-my/index.md).  
  
## <a name="adding-a-reference"></a>Hinzufügen eines Verweises  
 Bevor Sie die `MyServices`-Klassen in Ihrer Projektmappe verwenden, müssen Sie einen Verweis auf die Visual Basic-Bibliothek hinzufügen.  
  
#### <a name="to-add-a-reference-to-the-visual-basic-library"></a>So fügen Sie einen Verweis auf die Visual Basic-Bibliothek hinzu  
  
1.  Klicken Sie in **Projektmappen-Explorer** mit der rechten Maustaste auf den Knoten **Verweise** dann auf **Verweis hinzufügen**.  
  
2.  Wenn das Dialogfeld **Verweise** geöffnet wird, durchscrollen Sie die Liste, und klicken Sie auf „Microsoft.VisualBasic.dll“.  
  
     Sie sollten auch die folgende Zeile im Abschnitt `using` am Anfang Ihres Programms einfügen.  
  
     [!code-csharp[csProgGuideNamespaces#18](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-my-namespace_1.cs)]  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel werden mehrere statische Methoden aufgerufen, die im `MyServices`-Namespace enthalten sind. Damit dieser Code kompiliert wird, muss dem Projekt ein Verweis auf „Microsoft.VisualBasic.dll“ hinzugefügt werden.  
  
 [!code-csharp[csProgGuideNamespaces#19](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-my-namespace_2.cs)]  
  
 Nicht alle Klassen des `MyServices`-Namespace können aus einer C#-Anwendung aufgerufen werden: die <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy>-Klasse ist z.B. nicht kompatibel. In diesem Fall können stattdessen die statischen Methoden verwendet werden, die Teil von <xref:Microsoft.VisualBasic.FileIO.FileSystem> sind und die außerdem in „VisualBasic.dll“ enthalten sind. So können Sie z.B. eine derartige Methode verwenden, um ein Verzeichnis zu duplizieren:  
  
 [!code-csharp[csProgGuideNamespaces#20](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-my-namespace_3.cs)]  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [Namespaces](../../../csharp/programming-guide/namespaces/index.md)  
 [Using-Namespaces](../../../csharp/programming-guide/namespaces/using-namespaces.md)

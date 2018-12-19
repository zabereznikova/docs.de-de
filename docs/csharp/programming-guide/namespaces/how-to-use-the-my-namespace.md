---
title: 'Vorgehensweise: Verwenden des My-Namespaces – C#-Programmierhandbuch'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, My namespace access
ms.assetid: e7152414-0ea5-4c8e-bf02-c8d5bbe45ff4
ms.openlocfilehash: 00f9083fb9d0ef6c96e19e085a6cff0e0e36f2b0
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2018
ms.locfileid: "53236712"
---
# <a name="how-to-use-the-my-namespace-c-programming-guide"></a>Vorgehensweise: Verwenden des My-Namespaces (C#-Programmierhandbuch)
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

- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
- [Namespaces](../../../csharp/programming-guide/namespaces/index.md)  
- [Using-Namespaces](../../../csharp/programming-guide/namespaces/using-namespaces.md)

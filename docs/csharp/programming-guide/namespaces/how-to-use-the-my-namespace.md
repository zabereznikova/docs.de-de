---
title: 'Vorgehensweise: Verwenden des My-Namespaces (C#-Programmierleitfaden)'
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, My namespace access
ms.assetid: e7152414-0ea5-4c8e-bf02-c8d5bbe45ff4
ms.openlocfilehash: 063b46a32ced859c6c86e40c4a6b9870c3decd24
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "75700418"
---
# <a name="how-to-use-the-my-namespace-c-programming-guide"></a>Vorgehensweise: Verwenden des My-Namespaces (C#-Programmierleitfaden)
Der <xref:Microsoft.VisualBasic.MyServices>-Namespace (`My` in Visual Basic) bietet einfachen und intuitiven Zugriff auf mehrere .NET Framework-Klassen, mit denen Sie Code schreiben können, der mit dem Computer, der Anwendung, den Einstellungen, den Ressourcen usw. interagiert. Auch wenn er ursprünglich für Visual Basic entwickelt wurde, kann der `MyServices`-Namespace auch in C#-Anwendungen verwendet werden.  
  
 Weitere Informationen zum Verwenden des `MyServices`-Namespace in Visual Basic finden Sie unter [Development with My (Entwicklung mit „My“)](../../../visual-basic/developing-apps/development-with-my/index.md).  
  
## <a name="adding-a-reference"></a>Hinzufügen eines Verweises  
 Bevor Sie die `MyServices`-Klassen in Ihrer Projektmappe verwenden, müssen Sie einen Verweis auf die Visual Basic-Bibliothek hinzufügen.  
  
#### <a name="to-add-a-reference-to-the-visual-basic-library"></a>So fügen Sie einen Verweis auf die Visual Basic-Bibliothek hinzu  
  
1. Klicken Sie in **Projektmappen-Explorer** mit der rechten Maustaste auf den Knoten **Verweise** dann auf **Verweis hinzufügen**.  
  
2. Wenn das Dialogfeld **Verweise** geöffnet wird, durchscrollen Sie die Liste, und klicken Sie auf „Microsoft.VisualBasic.dll“.  
  
     Sie sollten auch die folgende Zeile im Abschnitt `using` am Anfang Ihres Programms einfügen.  
  
     [!code-csharp[csProgGuideNamespaces#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces3.cs#18)]  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel werden mehrere statische Methoden aufgerufen, die im `MyServices`-Namespace enthalten sind. Damit dieser Code kompiliert wird, muss dem Projekt ein Verweis auf „Microsoft.VisualBasic.dll“ hinzugefügt werden.  
  
 [!code-csharp[csProgGuideNamespaces#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces3.cs#19)]  
  
 Nicht alle Klassen des `MyServices`-Namespace können aus einer C#-Anwendung aufgerufen werden: die <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy>-Klasse ist z.B. nicht kompatibel. In diesem Fall können stattdessen die statischen Methoden verwendet werden, die Teil von <xref:Microsoft.VisualBasic.FileIO.FileSystem> sind und die außerdem in „VisualBasic.dll“ enthalten sind. So können Sie z.B. eine derartige Methode verwenden, um ein Verzeichnis zu duplizieren:  
  
 [!code-csharp[csProgGuideNamespaces#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces3.cs#20)]  
  
## <a name="see-also"></a>Weitere Informationen

- [C#-Programmierhandbuch](../index.md)
- [Namespaces](./index.md)
- [Using-Namespaces](./using-namespaces.md)

---
title: 'Gewusst wie: Hinzufügen von Webbrowserfunktionen zu einer Windows Forms-Anwendung'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- WebBrowser control [Windows Forms], adding Web browser capabilities to your application
- WebBrowser control [Windows Forms], examples
- Web browsers [.NET Framework], adding to Windows Forms
- examples [Windows Forms], WebBrowser control
- Windows Forms, adding Web browser functionality
ms.assetid: 3871f072-b57a-435b-9976-e5da28df04a7
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3e7cde23c7395e778f8f6cf9b13f998dded18d69
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-add-web-browser-capabilities-to-a-windows-forms-application"></a>Gewusst wie: Hinzufügen von Webbrowserfunktionen zu einer Windows Forms-Anwendung
Mit dem <xref:System.Windows.Forms.WebBrowser>-Steuerelement können Sie Webbrowserfunktionalität in Ihre Anwendung einbinden. Das Steuerelement verhält sich standardmäßig wie ein Webbrowser. Nach dem Laden einer Anfangs-URL durch Festlegen der <xref:System.Windows.Forms.WebBrowser.Url%2A>-Eigenschaft können Sie auf Hyperlinks klicken oder mit den entsprechenden Tastenkombinationen vorwärts oder rückwärts durch den Navigationsverlauf navigieren. Über das Kontextmenü, das durch Klicken mit der rechten Maustaste angezeigt wird, können standardmäßig zusätzliche Browserfunktionen aufgerufen werden. Sie können auch neue Dokumente öffnen, indem Sie sie auf dem Steuerelement ablegen. Das <xref:System.Windows.Forms.WebBrowser>-Steuerelement verfügt über verschiedene Eigenschaften, Methoden und Ereignisse, mit denen Sie ähnliche Benutzeroberflächenfeatures wie in Internet Explorer implementieren können.  
  
 Im folgenden Beispielcode werden eine Adressleiste, typische Browserschaltflächen, ein Menü **Datei**, eine Statusleiste und eine Titelleiste mit dem Titel der aktuellen Seite implementiert.  
  
## <a name="example"></a>Beispiel  
 [!code-cpp[System.Windows.Forms.WebBrowser#0](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser/CPP/form1.cpp#0)]
 [!code-csharp[System.Windows.Forms.WebBrowser#0](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser/CS/form1.cs#0)]
 [!code-vb[System.Windows.Forms.WebBrowser#0](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser/VB/form1.vb#0)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Verweise auf die `System,``System.Drawing`-Assembly und die `System.Windows.Forms`-Assembly.  
  
 Informationen zum Erstellen dieses Beispiels über die Befehlszeile für Visual Basic oder Visual c# finden Sie unter [erstellen über die Befehlszeile](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Befehlszeile mit csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). Sie können dieses Beispiel auch in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] erstellen, indem Sie den Code in ein neues Projekt einfügen.  Siehe auch [Gewusst wie: Kompilieren und Ausführen eines vollständigen Windows Forms-Codebeispiels mit Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.WebBrowser>  
 [WebBrowser-Steuerelement](../../../../docs/framework/winforms/controls/webbrowser-control-windows-forms.md)

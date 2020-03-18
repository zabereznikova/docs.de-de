---
title: 'Gewusst wie: Schreiben von Text in Dateien im Verzeichnis "Eigene Dateien"'
ms.date: 07/20/2015
helpviewer_keywords:
- files [Visual Basic], writing to
- text, writing to files
- examples [Visual Basic], text files
- writing to files [Visual Basic], in My Documents
ms.assetid: 1c726124-781d-4976-9baa-ed46814ff3fe
ms.openlocfilehash: bc62f2bc63a2ea185b8ea4c8d271dd28d347d6f0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "74334527"
---
# <a name="how-to-write-text-to-files-in-the-my-documents-directory-in-visual-basic"></a>Gewusst wie: Schreiben von Text in Dateien im Verzeichnis "Eigene Dateien" in Visual Basic

Mit dem `My.Computer.FileSystem.SpecialDirectories`-Objekt können Sie auf besondere Verzeichnisse zugreifen, wie z.B. das Verzeichnis **MyDocuments**.  
  
## <a name="procedure"></a>Prozedur  
  
#### <a name="to-write-new-text-files-in-the-my-documents-directory"></a>Schreiben von Text in Dateien im Verzeichnis „Eigene Dokumente“  
  
1. Verwenden Sie die `My.Computer.FileSystem.SpecialDirectories.MyDocuments`-Eigenschaft, um den Pfad bereitzustellen.  
  
     [!code-vb[VbFileIOWrite#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIOWrite/VB/Class1.vb#1)]  
  
2. Verwenden Sie die `WriteAllText`-Methode, um Text in eine angegebene Datei zu schreiben.  
  
     [!code-vb[VbVbcnMyFileSystem#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#14)]  
  
## <a name="example"></a>Beispiel  

 [!code-vb[VbFileIOWrite#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIOWrite/VB/Class1.vb#2)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  

 Ersetzen Sie `test.txt` durch den Namen der Datei, in die Sie schreiben möchten.  
  
## <a name="robust-programming"></a>Stabile Programmierung  

 Durch diesen Code werden die Ausnahmen erneut ausgelöst, die möglicherweise beim Schreiben von Text in eine Datei auftreten. Sie können die Wahrscheinlichkeit des Auftretens von Ausnahmen verringern, indem Sie Steuerelemente von Windows Forms, wie z.B. die Komponenten [OpenFileDialog](../../../../framework/winforms/controls/openfiledialog-component-windows-forms.md) und [SaveFileDialog](../../../../framework/winforms/controls/savefiledialog-component-windows-forms.md) verwenden, die den Benutzer nur aus zulässigen Namen wählen lassen. Das Verwenden dieser Steuerelemente ist jedoch nicht narrensicher. Das Dateisystem kann sich zwischen dem Zeitpunkt, an dem der Benutzer eine Datei auswählt, und dem Ausführen des Codes ändern. Das Behandeln von Ausnahmen ist deshalb beim Arbeiten mit Dateien fast immer notwendig.  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  

 Wenn Sie in einem teilweise vertrauenswürdigen Kontext arbeiten, kann der Code möglicherweise aufgrund fehlender Berechtigungen eine Ausnahme auslösen. Weitere Informationen finden Sie unter [Code Access Security Basics](../../../../framework/misc/code-access-security-basics.md).  
  
 In diesem Beispiel wird eine neue Datei erstellt. Wenn eine Anwendung eine Datei erstellen muss, benötigt sie eine Berechtigung zum Erstellen für den Ordner. Berechtigungen werden mithilfe von Zugriffssteuerungslisten festgelegt. Wenn die Datei bereits vorhanden ist, benötigt die Anwendung lediglich eine Schreibberechtigung, was einer geringeren Berechtigung entspricht. Aus Sicherheitsgründen sollte die Datei nach Möglichkeit erst im Verlauf der Bereitstellung erstellt werden. Außerdem sollte nur die Leseberechtigung für eine einzelne Datei erteilt werden (anstatt Erstellberechtigungen für den gesamten Ordner zu gewähren). Darüber hinaus ist es sicherer, Daten in Benutzerordner statt in Stammordner oder den Ordner **Programme** zu schreiben. Weitere Informationen finden Sie unter [Übersicht über die ACL-Technologie](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms229742(v=vs.100)).  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.IO.Path.Combine%2A?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Devices.Computer>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A>
- <xref:Microsoft.VisualBasic.FileIO.SpecialDirectories>

---
title: 'Gewusst wie: Festlegen des vom ProgressBar-Steuerelement für Windows Forms angezeigten Werts'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ProgressBar control [Windows Forms], setting value displayed
- progress controls [Windows Forms], setting value displayed
ms.assetid: 0e5010ad-1e9a-4271-895e-5a3d24d37a26
ms.openlocfilehash: 66093cacea4f76ab65af40658f03c03ce7560f0d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-set-the-value-displayed-by-the-windows-forms-progressbar-control"></a>Gewusst wie: Festlegen des vom ProgressBar-Steuerelement für Windows Forms angezeigten Werts
> [!IMPORTANT]
>  Obwohl das <xref:System.Windows.Forms.ToolStripProgressBar>-Steuerelement das <xref:System.Windows.Forms.ProgressBar>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.ProgressBar>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.  
  
 Die [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] bietet Ihnen mehrere Möglichkeiten zum Anzeigen eines angegebenen Werts innerhalb der <xref:System.Windows.Forms.ProgressBar> Steuerelement. Welchen Ansatz Sie auswählen, hängt von der Aufgabe oder das Problem, das Sie lösen möchten. Die folgende Tabelle zeigt die Ansätze, die Sie auswählen können.  
  
|Ansatz|Beschreibung|  
|--------------|-----------------|  
|Legen Sie den Wert, der die <xref:System.Windows.Forms.ProgressBar> direkt steuern.|Dieser Ansatz eignet sich für Aufgaben wissen Sie, wo die Summe des gemessenen Elements, die beteiligt sein wird, z. B. Datensätze aus einer Datenquelle lesen. Wenn Sie nur den Wert ein-oder zweimal festlegen müssen, ist dies eine einfache Möglichkeit, zu diesem Zweck. Abschließend verwenden Sie diesen Prozess, verringern Sie den Wert der Statusanzeige angezeigt werden sollen.|  
|Erhöhen Sie die <xref:System.Windows.Forms.ProgressBar> anzeigen, indem Sie ein fester Wert.|Dieser Ansatz ist hilfreich, wenn Sie eine einfache Angabe zwischen die Mindest- und Höchstwerte, z. B. die verstrichene Zeit oder die Anzahl der Dateien, die von einer bekannten insgesamt verarbeitet wurden anzeigen.|  
|Erhöhen Sie die <xref:System.Windows.Forms.ProgressBar> anzeigen, indem ein Wert, der variiert.|Dieser Ansatz ist hilfreich, wenn Sie zum Ändern des angezeigten Werts eine Anzahl von Malen in unterschiedlichen Mengen müssen. Ein Beispiel wäre die Menge an Festplattenspeicher konsumiert beim Versuch, eine Reihe von Dateien auf den Datenträger schreiben angezeigt werden.|  
  
 Die einfachste Möglichkeit zum Festlegen des Werts von einer Statusanzeige angezeigt wird, durch Festlegen der <xref:System.Windows.Forms.ProgressBar.Value%2A> Eigenschaft. Dies kann zur Entwurfszeit oder zur Laufzeit erfolgen.  
  
### <a name="to-set-the-progressbar-value-directly"></a>Den Wert "ProgressBar" direkt festgelegt.  
  
1.  Legen Sie die <xref:System.Windows.Forms.ProgressBar> des Steuerelements <xref:System.Windows.Forms.ProgressBar.Minimum%2A> und <xref:System.Windows.Forms.ProgressBar.Maximum%2A> Werte.  
  
2.  Legen Sie im Code des Steuerelements <xref:System.Windows.Forms.ProgressBar.Value%2A> Eigenschaft auf einen ganzzahligen Wert zwischen der minimalen und maximalen Werte, die Sie eingerichtet haben.  
  
    > [!NOTE]
    >  Wenn Sie festlegen, die <xref:System.Windows.Forms.ProgressBar.Value%2A> Eigenschaft außerhalb der Grenzen von der <xref:System.Windows.Forms.ProgressBar.Minimum%2A> und <xref:System.Windows.Forms.ProgressBar.Maximum%2A> Eigenschaften, löst das Steuerelement eine <xref:System.ArgumentException> Ausnahme.  
  
     Im folgenden Codebeispiel wird veranschaulicht, wie zum Festlegen der <xref:System.Windows.Forms.ProgressBar> Wert direkt. Der Code liest Datensätze aus einer Datenquelle und der Statusanzeige und die Beschriftung jedes Mal aktualisiert ein Datensatz gelesen wird. Dieses Beispiel benötigen Sie, dass das Formular verfügt über eine <xref:System.Windows.Forms.Label> -Steuerelement, ein <xref:System.Windows.Forms.ProgressBar> -Steuerelement, und eine Datentabelle mit einer Zeile aufgerufen `CustomerRow` mit `FirstName` und `LastName` Felder.  
  
    ```vb  
    Public Sub CreateNewRecords()  
       ' Sets the progress bar's Maximum property to  
       ' the total number of records to be created.  
       ProgressBar1.Maximum = 20  
  
       ' Creates a new record in the dataset.  
       ' NOTE: The code below will not compile, it merely  
       ' illustrates how the progress bar would be used.  
       Dim anyRow As CustomerRow = DatasetName.ExistingTable.NewRow  
       anyRow.FirstName = "Stephen"  
       anyRow.LastName = "James"  
       ExistingTable.Rows.Add(anyRow)  
  
       ' Increases the value displayed by the progress bar.  
       ProgressBar1.Value += 1  
       ' Updates the label to show that a record was read.  
       Label1.Text = "Records Read = " & ProgressBar1.Value.ToString()  
    End Sub  
    ```  
  
    ```csharp  
    public void createNewRecords()  
    {  
       // Sets the progress bar's Maximum property to  
       // the total number of records to be created.  
       progressBar1.Maximum = 20;  
  
       // Creates a new record in the dataset.  
       // NOTE: The code below will not compile, it merely  
       // illustrates how the progress bar would be used.  
       CustomerRow anyRow = DatasetName.ExistingTable.NewRow();  
       anyRow.FirstName = "Stephen";  
       anyRow.LastName = "James";  
       ExistingTable.Rows.Add(anyRow);  
  
       // Increases the value displayed by the progress bar.  
       progressBar1.Value += 1;  
       // Updates the label to show that a record was read.  
       label1.Text = "Records Read = " + progressBar1.Value.ToString();  
    }  
    ```  
  
     Wenn Sie Verlauf, die nach einem festen Intervall wird fortgesetzt anzeigen, können Sie legen Sie den Wert und rufen Sie eine Methode, die erhöht die <xref:System.Windows.Forms.ProgressBar> Steuerelementwert von diesem Intervall. Dies ist hilfreich für Timer und andere Szenarien, in denen Sie Status nicht als Prozentsatz des ganzen messen.  
  
### <a name="to-increase-the-progress-bar-by-a-fixed-value"></a>Um die Statusanzeige durch einen festen Wert zu erhöhen.  
  
1.  Legen Sie die <xref:System.Windows.Forms.ProgressBar> des Steuerelements <xref:System.Windows.Forms.ProgressBar.Minimum%2A> und <xref:System.Windows.Forms.ProgressBar.Maximum%2A> Werte.  
  
2.  Legen Sie das Steuerelement <xref:System.Windows.Forms.ProgressBar.Step%2A> -Eigenschaft in eine ganze Zahl, die Menge darstellt, erhöhen Sie der Statusanzeige der angezeigte Wert.  
  
3.  Rufen Sie die <xref:System.Windows.Forms.ProgressBar.PerformStep%2A> Methode zum Ändern des Werts angezeigt, die für die festgelegte Wert die <xref:System.Windows.Forms.ProgressBar.Step%2A> Eigenschaft.  
  
     Im folgenden Codebeispiel wird veranschaulicht, wie eine Statusanzeige Anzahl der Dateien in einen Kopiervorgang verwalten kann.  
  
     Im folgenden Beispiel sobald jeder Datei in den Arbeitsspeicher gelesen werden kann sind der Statusanzeige und die Beschriftung entsprechend aktualisiert, dass die gesamte Dateien lesen. Dieses Beispiel benötigen Sie, dass das Formular verfügt über eine <xref:System.Windows.Forms.Label> Steuerelement und ein <xref:System.Windows.Forms.ProgressBar> Steuerelement.  
  
    ```vb  
    Public Sub LoadFiles()  
       ' Sets the progress bar's minimum value to a number representing  
       ' no operations complete -- in this case, no files read.  
       ProgressBar1.Minimum = 0  
       ' Sets the progress bar's maximum value to a number representing  
       ' all operations complete -- in this case, all five files read.  
       ProgressBar1.Maximum = 5  
       ' Sets the Step property to amount to increase with each iteration.  
       ' In this case, it will increase by one with every file read.  
       ProgressBar1.Step = 1  
  
       ' Dimensions a counter variable.  
       Dim i As Integer  
       ' Uses a For...Next loop to iterate through the operations to be  
       ' completed. In this case, five files are to be copied into memory,  
       ' so the loop will execute 5 times.  
       For i = 0 To 4  
          ' Insert code to copy a file  
          ProgressBar1.PerformStep()  
          ' Update the label to show that a file was read.  
          Label1.Text = "# of Files Read = " & ProgressBar1.Value.ToString  
       Next i  
    End Sub  
    ```  
  
    ```csharp  
    public void loadFiles()  
    {  
       // Sets the progress bar's minimum value to a number representing  
       // no operations complete -- in this case, no files read.  
       progressBar1.Minimum = 0;  
       // Sets the progress bar's maximum value to a number representing  
       // all operations complete -- in this case, all five files read.  
       progressBar1.Maximum = 5;  
       // Sets the Step property to amount to increase with each iteration.  
       // In this case, it will increase by one with every file read.  
       progressBar1.Step = 1;  
  
       // Uses a for loop to iterate through the operations to be  
       // completed. In this case, five files are to be copied into memory,  
       // so the loop will execute 5 times.  
       for (int i = 0; i <= 4; i++)  
       {  
          // Inserts code to copy a file  
          progressBar1.PerformStep();  
          // Updates the label to show that a file was read.  
          label1.Text = "# of Files Read = " + progressBar1.Value.ToString();  
       }  
    }  
    ```  
  
     Schließlich können Sie den Wert durch eine Statusanzeige angezeigt wird, sodass jede Erhöhung einer eindeutigen Menge ist, erhöhen. Dies ist hilfreich, wenn Sie nachverfolgt eine Reihe von eindeutigen Vorgänge, z. B. das Schreiben von Dateien mit verschiedenen Größen auf einer Festplatte oder Messen des Fortschritts als Prozentsatz des ganzen sind.  
  
### <a name="to-increase-the-progress-bar-by-a-dynamic-value"></a>Die Statusanzeige um einen dynamischen Wert zu erhöhen  
  
1.  Legen Sie die <xref:System.Windows.Forms.ProgressBar> des Steuerelements <xref:System.Windows.Forms.ProgressBar.Minimum%2A> und <xref:System.Windows.Forms.ProgressBar.Maximum%2A> Werte.  
  
2.  Rufen Sie die <xref:System.Windows.Forms.ProgressBar.Increment%2A> Methode so ändern Sie die angezeigte Wert um eine ganze Zahl, die Sie angeben.  
  
     Im folgenden Codebeispiel wird veranschaulicht, wie eine Statusanzeige berechnen kann, wie viel Speicherplatz während eines Kopiervorgangs verwendet wurde.  
  
     Im folgenden Beispiel, wenn jede Datei auf die Festplatte geschrieben wird werden die Statusanzeige und eine Bezeichnung entsprechend aktualisiert die Menge an Festplattenspeicher zur Verfügung. Dieses Beispiel benötigen Sie, dass das Formular verfügt über eine <xref:System.Windows.Forms.Label> Steuerelement und ein <xref:System.Windows.Forms.ProgressBar> Steuerelement.  
  
    ```vb  
    Public Sub ReadFiles()  
       ' Sets the progress bar's minimum value to a number   
       ' representing the hard disk space before the files are read in.  
       ' You will most likely have to set this using a system call.  
       ' NOTE: The code below is meant to be an example and  
       ' will not compile.  
       ProgressBar1.Minimum = AvailableDiskSpace()  
       ' Sets the progress bar's maximum value to a number   
       ' representing the total hard disk space.  
       ' You will most likely have to set this using a system call.  
       ' NOTE: The code below is meant to be an example   
       ' and will not compile.  
       ProgressBar1.Maximum = TotalDiskSpace()  
  
       ' Dimension a counter variable.  
       Dim i As Integer  
       ' Uses a For...Next loop to iterate through the operations to be  
       ' completed. In this case, five files are to be written to the disk,  
       ' so it will execute the loop 5 times.  
       For i = 1 To 5  
          ' Insert code to read a file into memory and update file size.  
          ' Increases the progress bar's value based on the size of   
          ' the file currently being written.  
          ProgressBar1.Increment(FileSize)  
          ' Updates the label to show available drive space.  
          Label1.Text = "Current Disk Space Used = " &_   
          ProgressBar1.Value.ToString()  
       Next i  
    End Sub  
    ```  
  
    ```csharp  
    public void readFiles()  
    {  
       // Sets the progress bar's minimum value to a number   
       // representing the hard disk space before the files are read in.  
       // You will most likely have to set this using a system call.  
       // NOTE: The code below is meant to be an example and   
       // will not compile.  
       progressBar1.Minimum = AvailableDiskSpace();  
       // Sets the progress bar's maximum value to a number   
       // representing the total hard disk space.  
       // You will most likely have to set this using a system call.  
       // NOTE: The code below is meant to be an example   
       // and will not compile.  
       progressBar1.Maximum = TotalDiskSpace();  
  
       // Uses a for loop to iterate through the operations to be  
       // completed. In this case, five files are to be written  
       // to the disk, so it will execute the loop 5 times.  
       for (int i = 1; i<= 5; i++)  
       {  
          // Insert code to read a file into memory and update file size.  
          // Increases the progress bar's value based on the size of   
          // the file currently being written.  
          progressBar1.Increment(FileSize);  
          // Updates the label to show available drive space.  
          label1.Text = "Current Disk Space Used = " + progressBar1.Value.ToString();  
       }  
    }  
    ```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.ProgressBar>  
 <xref:System.Windows.Forms.ToolStripProgressBar>  
 [Übersicht über das ProgressBar-Steuerelement](../../../../docs/framework/winforms/controls/progressbar-control-overview-windows-forms.md)  
 [ProgressBar-Steuerelement](../../../../docs/framework/winforms/controls/progressbar-control-windows-forms.md)

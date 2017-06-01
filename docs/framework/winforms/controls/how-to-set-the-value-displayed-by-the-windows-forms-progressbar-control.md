---
title: "Gewusst wie: Festlegen des vom ProgressBar-Steuerelement f&#252;r Windows&#160;Forms angezeigten Werts | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Increment-Methode"
  - "PerformStep-Methode"
  - "Statussteuerelemente, Festlegen des angezeigten Werts"
  - "ProgressBar-Steuerelement [Windows Forms], Festlegen des angezeigten Werts"
  - "Step-Eigenschaft"
  - "Value-Eigenschaft"
ms.assetid: 0e5010ad-1e9a-4271-895e-5a3d24d37a26
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Gewusst wie: Festlegen des vom ProgressBar-Steuerelement f&#252;r Windows&#160;Forms angezeigten Werts
> [!IMPORTANT]
>  Obwohl das <xref:System.Windows.Forms.ToolStripProgressBar>\-Steuerelement das <xref:System.Windows.Forms.ProgressBar>\-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.ProgressBar>\-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.  
  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] bietet mehrere Möglichkeiten für das Anzeigen eines bestimmten Werts im <xref:System.Windows.Forms.ProgressBar>\-Steuerelement.  Die geeignete Vorgehensweise hängt davon ab, welche Aufgabe Sie durchführen bzw. welches Problem Sie lösen möchten.  Die folgende Tabelle zeigt die möglichen Vorgehensweisen.  
  
|Vorgehensweise|Beschreibung|  
|--------------------|------------------|  
|Sie können den Wert des <xref:System.Windows.Forms.ProgressBar>\-Steuerelements direkt festlegen.|Dies ist sinnvoll, wenn die relevante Gesamtmenge des gemessenen Elements bekannt ist, z. B. beim Lesen von Datensätzen aus einer Datenquelle.  Wenn Sie den Wert nur ein\- oder zweimal festlegen müssen, ist dies ebenfalls die geeignete Vorgehensweise.  Außerdem sollten Sie diesen Vorgang verwenden, wenn Sie den in der Statusanzeige angezeigten Wert verringern müssen.|  
|Sie können die <xref:System.Windows.Forms.ProgressBar>\-Anzeige um einen festen Wert erhöhen.|Dies ist sinnvoll, wenn Sie eine einfache Zählung zwischen dem Mindest\- und dem Höchstwert anzeigen möchten, z. B. die verstrichene Zeit oder die Anzahl der Dateien aus einer bekannten Gesamtmenge, die verarbeitet wurden.|  
|Sie können die <xref:System.Windows.Forms.ProgressBar>\-Anzeige um einen variablen Wert erhöhen.|Dies ist sinnvoll, wenn Sie den angezeigten Wert mehrfach in unterschiedlicher Höhe ändern müssen.  Ein Beispiel dafür wäre das Anzeigen des Festplattenspeichers, der beim Schreiben mehrerer Dateien auf die Festplatte belegt wird.|  
  
 Am einfachsten können Sie den von einer Statusanzeige angezeigten Wert festlegen, indem Sie die <xref:System.Windows.Forms.ProgressBar.Value%2A>\-Eigenschaft festlegen.  Dies ist sowohl zur Entwurfszeit als auch zur Laufzeit möglich.  
  
### So legen Sie den ProgressBar\-Wert fest  
  
1.  Legen Sie den <xref:System.Windows.Forms.ProgressBar.Minimum%2A>\-Wert und den <xref:System.Windows.Forms.ProgressBar.Maximum%2A>\-Wert des <xref:System.Windows.Forms.ProgressBar>\-Steuerelements fest.  
  
2.  Legen Sie im Code für die <xref:System.Windows.Forms.ProgressBar.Value%2A>\-Eigenschaft einen ganzzahligen Wert zwischen den von Ihnen festgelegten Minimal\- und Maximalwerten fest.  
  
    > [!NOTE]
    >  Wenn Sie die <xref:System.Windows.Forms.ProgressBar.Value%2A>\-Eigenschaft auf einen Wert außerhalb der durch die <xref:System.Windows.Forms.ProgressBar.Minimum%2A>\-Eigenschaft und die <xref:System.Windows.Forms.ProgressBar.Maximum%2A>\-Eigenschaft angegebenen Grenzen festlegen, löst das Steuerelement eine <xref:System.ArgumentException>\-Ausnahme aus.  
  
     Das folgende Beispiel zeigt das direkte Festlegen des <xref:System.Windows.Forms.ProgressBar>\-Werts.  Der Code liest Datensätze aus einer Datenquelle und aktualisiert bei jedem eingelesenen Datensatz die Statusanzeige und die Beschriftung.  In diesem Beispiel wird davon ausgegangen, dass das Formular über ein <xref:System.Windows.Forms.Label>\-Steuerelement, ein <xref:System.Windows.Forms.ProgressBar>\-Steuerelement und eine Datentabelle verfügt, die eine Zeile mit der Bezeichnung `CustomerRow`  und den Feldern `FirstName`  und `Last Name`  enthält.  
  
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
  
     Wenn Sie einen Verlauf anzeigen möchten, der in festen Intervallen fortschreitet, können Sie den Wert festlegen und anschließend eine Methode aufrufen, die den Wert des <xref:System.Windows.Forms.ProgressBar>\-Steuerelements um dieses Intervall erhöht.  Dies ist sinnvoll bei Zeitgebern und in anderen Fällen, in denen Sie den Verlauf nicht als Prozentsatz eines Ganzen ermitteln.  
  
### So erhöhen Sie die Statusanzeige um einen festen Wert  
  
1.  Legen Sie den <xref:System.Windows.Forms.ProgressBar.Minimum%2A>\-Wert und den <xref:System.Windows.Forms.ProgressBar.Maximum%2A>\-Wert des <xref:System.Windows.Forms.ProgressBar>\-Steuerelements fest.  
  
2.  Legen Sie die <xref:System.Windows.Forms.ProgressBar.Step%2A>\-Eigenschaft des Steuerelements auf einen ganzzahligen Wert fest, um den der angezeigte Wert der Statusanzeige erhöht werden soll.  
  
3.  Rufen Sie die <xref:System.Windows.Forms.ProgressBar.PerformStep%2A>\-Methode auf, um den angezeigten Wert um den in der <xref:System.Windows.Forms.ProgressBar.Step%2A>\-Eigenschaft festgelegten Wert zu erhöhen.  
  
     Das folgende Codebeispiel zeigt, wie eine Statusanzeige die Zählung der Dateien in einem Kopiervorgang verwaltet.  
  
     Im folgenden Beispiel werden die Statusanzeige und die Beschriftung auf die Gesamtanzahl der gelesenen Dateien aktualisiert, während die einzelnen Dateien in den Speicher eingelesen werden.  In diesem Beispiel wird davon ausgegangen, dass das Formular über ein <xref:System.Windows.Forms.Label>\-Steuerelement und ein <xref:System.Windows.Forms.ProgressBar>\-Steuerelement verfügt.  
  
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
  
     Sie können den von einer Statusanzeige angezeigten Wert auch in jedem Schritt um einen anderen Betrag erhöhen.  Dies ist sinnvoll, wenn Sie mehrere einzelne Vorgänge protokollieren, z. B. beim Schreiben von Dateien unterschiedlicher Größe auf eine Festplatte oder beim Ermitteln des Verlaufs als Prozentsatz eines Ganzen.  
  
### So erhöhen Sie die Statusanzeige um einen dynamischen Wert  
  
1.  Legen Sie den <xref:System.Windows.Forms.ProgressBar.Minimum%2A>\-Wert und den <xref:System.Windows.Forms.ProgressBar.Maximum%2A>\-Wert des <xref:System.Windows.Forms.ProgressBar>\-Steuerelements fest.  
  
2.  Rufen Sie die <xref:System.Windows.Forms.ProgressBar.Increment%2A>\-Methode auf, um den angezeigten Wert um einen von Ihnen angegebenen ganzzahligen Wert zu erhöhen.  
  
     Das folgende Codebeispiel zeigt, wie eine Statusanzeige den während eines Kopiervorgangs verbrauchten Speicherplatz berechnet.  
  
     Im folgenden Beispiel werden die Statusanzeige und die Beschriftung entsprechend dem verfügbaren Festplattenspeicher aktualisiert, während die einzelnen Dateien auf die Festplatte geschrieben werden.  In diesem Beispiel wird davon ausgegangen, dass das Formular über ein <xref:System.Windows.Forms.Label>\-Steuerelement und ein <xref:System.Windows.Forms.ProgressBar>\-Steuerelement verfügt.  
  
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
  
## Siehe auch  
 <xref:System.Windows.Forms.ProgressBar>   
 <xref:System.Windows.Forms.ToolStripProgressBar>   
 [Übersicht über das ProgressBar\-Steuerelement](../../../../docs/framework/winforms/controls/progressbar-control-overview-windows-forms.md)   
 [ProgressBar\-Steuerelement](../../../../docs/framework/winforms/controls/progressbar-control-windows-forms.md)
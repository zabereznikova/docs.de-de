---
title: 'Vorgehensweise: Festlegen des vom ProgressBar-Steuerelement für Windows Forms angezeigten Werts'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ProgressBar control [Windows Forms], setting value displayed
- progress controls [Windows Forms], setting value displayed
ms.assetid: 0e5010ad-1e9a-4271-895e-5a3d24d37a26
ms.openlocfilehash: 42a9e0f67f00c1a706b72ab0eeb522e99d8a8dfe
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59300475"
---
# <a name="how-to-set-the-value-displayed-by-the-windows-forms-progressbar-control"></a><span data-ttu-id="5ba05-102">Vorgehensweise: Festlegen des vom ProgressBar-Steuerelement für Windows Forms angezeigten Werts</span><span class="sxs-lookup"><span data-stu-id="5ba05-102">How to: Set the Value Displayed by the Windows Forms ProgressBar Control</span></span>
> [!IMPORTANT]
>  <span data-ttu-id="5ba05-103">Obwohl das <xref:System.Windows.Forms.ToolStripProgressBar>-Steuerelement das <xref:System.Windows.Forms.ProgressBar>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.ProgressBar>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.</span><span class="sxs-lookup"><span data-stu-id="5ba05-103">The <xref:System.Windows.Forms.ToolStripProgressBar> control replaces and adds functionality to the <xref:System.Windows.Forms.ProgressBar> control; however, the <xref:System.Windows.Forms.ProgressBar> control is retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="5ba05-104">Die [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] bietet Ihnen mehrere Möglichkeiten zum Anzeigen eines angegebenen Werts innerhalb der <xref:System.Windows.Forms.ProgressBar> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="5ba05-104">The [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] gives you several different ways to display a given value within the <xref:System.Windows.Forms.ProgressBar> control.</span></span> <span data-ttu-id="5ba05-105">Welchen Ansatz Sie wählen, hängt die aktuelle Aufgabe oder das Problem, das Sie lösen.</span><span class="sxs-lookup"><span data-stu-id="5ba05-105">Which approach you choose will depend on the task at hand or the problem you are solving.</span></span> <span data-ttu-id="5ba05-106">Die folgende Tabelle zeigt die Ansätze, dass Sie auswählen können.</span><span class="sxs-lookup"><span data-stu-id="5ba05-106">The following table shows the approaches you can choose.</span></span>  
  
|<span data-ttu-id="5ba05-107">Ansatz</span><span class="sxs-lookup"><span data-stu-id="5ba05-107">Approach</span></span>|<span data-ttu-id="5ba05-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5ba05-108">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="5ba05-109">Legen Sie den Wert, der die <xref:System.Windows.Forms.ProgressBar> direkt steuern.</span><span class="sxs-lookup"><span data-stu-id="5ba05-109">Set the value of the <xref:System.Windows.Forms.ProgressBar> control directly.</span></span>|<span data-ttu-id="5ba05-110">Dieser Ansatz eignet sich für Aufgaben, in denen Sie die Summe des gemessenen Elements, die z. B. beim Lesen von Datensätzen aus einer Datenquelle beteiligt sein wird, wissen.</span><span class="sxs-lookup"><span data-stu-id="5ba05-110">This approach is useful for tasks where you know the total of the item measured that will be involved, such as reading records from a data source.</span></span> <span data-ttu-id="5ba05-111">Wenn Sie nur den Wert ein-oder zweimal festlegen müssen, ist dies eine einfache Möglichkeit dafür.</span><span class="sxs-lookup"><span data-stu-id="5ba05-111">Additionally, if you only need to set the value once or twice, this is an easy way to do it.</span></span> <span data-ttu-id="5ba05-112">Abschließend verwenden Sie diesen Prozess, verringern Sie den Wert, der von der Statusanzeige angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="5ba05-112">Finally, use this process if you need to decrease the value displayed by the progress bar.</span></span>|  
|<span data-ttu-id="5ba05-113">Erhöhen Sie die <xref:System.Windows.Forms.ProgressBar> anzeigen, indem Sie einen festen Wert.</span><span class="sxs-lookup"><span data-stu-id="5ba05-113">Increase the <xref:System.Windows.Forms.ProgressBar> display by a fixed value.</span></span>|<span data-ttu-id="5ba05-114">Dieser Ansatz ist hilfreich, wenn Sie einen einfachen Zähler zwischen der minimalen und maximalen, z. B. die verstrichene Zeit oder die Anzahl der Dateien, die von einer bekannten insgesamt verarbeitet wurden anzeigen.</span><span class="sxs-lookup"><span data-stu-id="5ba05-114">This approach is useful when you are displaying a simple count between the minimum and maximum, such as elapsed time or the number of files that have been processed out of a known total.</span></span>|  
|<span data-ttu-id="5ba05-115">Erhöhen Sie die <xref:System.Windows.Forms.ProgressBar> anzeigen, indem Sie einen Wert, der davon unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="5ba05-115">Increase the <xref:System.Windows.Forms.ProgressBar> display by a value that varies.</span></span>|<span data-ttu-id="5ba05-116">Dieser Ansatz ist nützlich, wenn Sie zum Ändern des angezeigten Werts eine Anzahl von Malen in unterschiedliche Mengen müssen.</span><span class="sxs-lookup"><span data-stu-id="5ba05-116">This approach is useful when you need to change the displayed value a number of times in different amounts.</span></span> <span data-ttu-id="5ba05-117">Ein Beispiel würde zeigen die Menge an Festplattenspeicher, die beim Schreiben einer Reihe von Dateien auf dem Datenträger verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="5ba05-117">An example would be showing the amount of hard-disk space being consumed while writing a series of files to the disk.</span></span>|  
  
 <span data-ttu-id="5ba05-118">Die direkteste Möglichkeit zum Festlegen des Werts von einer Statusanzeige angezeigt wird, durch Festlegen der <xref:System.Windows.Forms.ProgressBar.Value%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="5ba05-118">The most direct way to set the value displayed by a progress bar is by setting the <xref:System.Windows.Forms.ProgressBar.Value%2A> property.</span></span> <span data-ttu-id="5ba05-119">Dies kann entweder zur Entwurfszeit oder zur Laufzeit erfolgen.</span><span class="sxs-lookup"><span data-stu-id="5ba05-119">This can be done either at design time or at run time.</span></span>  
  
### <a name="to-set-the-progressbar-value-directly"></a><span data-ttu-id="5ba05-120">Den Wert "ProgressBar" direkt festgelegt.</span><span class="sxs-lookup"><span data-stu-id="5ba05-120">To set the ProgressBar value directly</span></span>  
  
1. <span data-ttu-id="5ba05-121">Legen Sie die <xref:System.Windows.Forms.ProgressBar> des Steuerelements <xref:System.Windows.Forms.ProgressBar.Minimum%2A> und <xref:System.Windows.Forms.ProgressBar.Maximum%2A> Werte.</span><span class="sxs-lookup"><span data-stu-id="5ba05-121">Set the <xref:System.Windows.Forms.ProgressBar> control's <xref:System.Windows.Forms.ProgressBar.Minimum%2A> and <xref:System.Windows.Forms.ProgressBar.Maximum%2A> values.</span></span>  
  
2. <span data-ttu-id="5ba05-122">Legen Sie im Code des Steuerelements <xref:System.Windows.Forms.ProgressBar.Value%2A> Eigenschaft, um eine ganze Zahl zwischen der minimalen und maximalen Werte, die Sie eingerichtet haben.</span><span class="sxs-lookup"><span data-stu-id="5ba05-122">In code, set the control's <xref:System.Windows.Forms.ProgressBar.Value%2A> property to an integer value between the minimum and maximum values you have established.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5ba05-123">Setzen Sie die <xref:System.Windows.Forms.ProgressBar.Value%2A> Eigenschaft außerhalb der Grenzen hergestellt, indem die <xref:System.Windows.Forms.ProgressBar.Minimum%2A> und <xref:System.Windows.Forms.ProgressBar.Maximum%2A> Eigenschaften, löst das Steuerelement eine <xref:System.ArgumentException> Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="5ba05-123">If you set the <xref:System.Windows.Forms.ProgressBar.Value%2A> property outside the boundaries established by the <xref:System.Windows.Forms.ProgressBar.Minimum%2A> and <xref:System.Windows.Forms.ProgressBar.Maximum%2A> properties, the control throws an <xref:System.ArgumentException> exception.</span></span>  
  
     <span data-ttu-id="5ba05-124">Im folgenden Codebeispiel wird veranschaulicht, wie zum Festlegen der <xref:System.Windows.Forms.ProgressBar> Wert direkt.</span><span class="sxs-lookup"><span data-stu-id="5ba05-124">The following code example illustrates how to set the <xref:System.Windows.Forms.ProgressBar> value directly.</span></span> <span data-ttu-id="5ba05-125">Der Code liest Datensätze aus einer Datenquelle und aktualisiert die Statusanzeige und eine Bezeichnung, jedes Mal, wenn ein Datensatz gelesen wird.</span><span class="sxs-lookup"><span data-stu-id="5ba05-125">The code reads records from a data source and updates the progress bar and label every time a data record is read.</span></span> <span data-ttu-id="5ba05-126">Dieses Beispiel erfordert, dass das Formular enthält ein <xref:System.Windows.Forms.Label> -Steuerelement, ein <xref:System.Windows.Forms.ProgressBar> -Steuerelement, und eine Datentabelle mit einer Zeile `CustomerRow` mit `FirstName` und `LastName` Felder.</span><span class="sxs-lookup"><span data-stu-id="5ba05-126">This example requires that your form has a <xref:System.Windows.Forms.Label> control, a <xref:System.Windows.Forms.ProgressBar> control, and a data table with a row called `CustomerRow` with `FirstName` and `LastName` fields.</span></span>  
  
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
  
     Wenn Sie Fortschritt, die nach einem festen Intervall fortgesetzt wird anzeigen, können Sie legen Sie den Wert und rufen Sie dann auf eine Methode, die erhöht die <xref:System.Windows.Forms.ProgressBar> Wert des Steuerelements nach diesem Intervall. <span data-ttu-id="5ba05-128">Dies ist nützlich für Zeitgeber und andere Szenarien, in dem Sie Fortschritt nicht als Prozentsatz des ganzen messen.</span><span class="sxs-lookup"><span data-stu-id="5ba05-128">This is useful for timers and other scenarios where you are not measuring progress as a percentage of the whole.</span></span>  
  
### <a name="to-increase-the-progress-bar-by-a-fixed-value"></a><span data-ttu-id="5ba05-129">Um die Statusanzeige durch einen festen Wert zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="5ba05-129">To increase the progress bar by a fixed value</span></span>  
  
1. <span data-ttu-id="5ba05-130">Legen Sie die <xref:System.Windows.Forms.ProgressBar> des Steuerelements <xref:System.Windows.Forms.ProgressBar.Minimum%2A> und <xref:System.Windows.Forms.ProgressBar.Maximum%2A> Werte.</span><span class="sxs-lookup"><span data-stu-id="5ba05-130">Set the <xref:System.Windows.Forms.ProgressBar> control's <xref:System.Windows.Forms.ProgressBar.Minimum%2A> and <xref:System.Windows.Forms.ProgressBar.Maximum%2A> values.</span></span>  
  
2. <span data-ttu-id="5ba05-131">Legen Sie die <xref:System.Windows.Forms.ProgressBar.Step%2A> -Eigenschaft eine ganze Zahl fest, die Menge der Statusanzeige erhöht der angezeigte Wert.</span><span class="sxs-lookup"><span data-stu-id="5ba05-131">Set the control's <xref:System.Windows.Forms.ProgressBar.Step%2A> property to an integer representing the amount to increase the progress bar's displayed value.</span></span>  
  
3. <span data-ttu-id="5ba05-132">Rufen Sie die <xref:System.Windows.Forms.ProgressBar.PerformStep%2A> Methode zum Ändern des Werts angezeigt wird, um den Betrag an, legen Sie in der <xref:System.Windows.Forms.ProgressBar.Step%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="5ba05-132">Call the <xref:System.Windows.Forms.ProgressBar.PerformStep%2A> method to change the value displayed by the amount set in the <xref:System.Windows.Forms.ProgressBar.Step%2A> property.</span></span>  
  
     <span data-ttu-id="5ba05-133">Im folgenden Codebeispiel wird veranschaulicht, wie eine Statusanzeige Anzahl der Dateien in einem Kopiervorgang verwalten kann.</span><span class="sxs-lookup"><span data-stu-id="5ba05-133">The following code example illustrates how a progress bar can maintain a count of the files in a copy operation.</span></span>  
  
     <span data-ttu-id="5ba05-134">Im folgenden Beispiel wie jede Datei in den Arbeitsspeicher zu lesen ist sind die Statusanzeige und eine Bezeichnung entsprechend aktualisiert, dass die gesamte Dateien lesen.</span><span class="sxs-lookup"><span data-stu-id="5ba05-134">In the following example, as each file is read into memory, the progress bar and label are updated to reflect the total files read.</span></span> <span data-ttu-id="5ba05-135">Dieses Beispiel erfordert, dass das Formular enthält ein <xref:System.Windows.Forms.Label> Steuerelement und ein <xref:System.Windows.Forms.ProgressBar> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="5ba05-135">This example requires that your form has a <xref:System.Windows.Forms.Label> control and a <xref:System.Windows.Forms.ProgressBar> control.</span></span>  
  
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
  
     Schließlich können Sie den Wert, der durch eine Statusanzeige angezeigt wird, sodass jede Erhöhung einer eindeutigen Menge ist, erhöhen. <span data-ttu-id="5ba05-137">Dies ist nützlich, wenn Sie nachverfolgt eine Reihe von eindeutigen Vorgänge, z. B. das Schreiben von Dateien mit verschiedenen Größen auf einer Festplatte oder als Prozentsatz des ganzen messen werden.</span><span class="sxs-lookup"><span data-stu-id="5ba05-137">This is useful when you are keeping track of a series of unique operations, such as writing files of different sizes to a hard disk, or measuring progress as a percentage of the whole.</span></span>  
  
### <a name="to-increase-the-progress-bar-by-a-dynamic-value"></a><span data-ttu-id="5ba05-138">Die Statusanzeige um einen dynamischen Wert zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="5ba05-138">To increase the progress bar by a dynamic value</span></span>  
  
1. <span data-ttu-id="5ba05-139">Legen Sie die <xref:System.Windows.Forms.ProgressBar> des Steuerelements <xref:System.Windows.Forms.ProgressBar.Minimum%2A> und <xref:System.Windows.Forms.ProgressBar.Maximum%2A> Werte.</span><span class="sxs-lookup"><span data-stu-id="5ba05-139">Set the <xref:System.Windows.Forms.ProgressBar> control's <xref:System.Windows.Forms.ProgressBar.Minimum%2A> and <xref:System.Windows.Forms.ProgressBar.Maximum%2A> values.</span></span>  
  
2. <span data-ttu-id="5ba05-140">Rufen Sie die <xref:System.Windows.Forms.ProgressBar.Increment%2A> Methode so ändern Sie den Wert, der durch eine ganze Zahl, die Sie angeben, angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5ba05-140">Call the <xref:System.Windows.Forms.ProgressBar.Increment%2A> method to change the value displayed by an integer you specify.</span></span>  
  
     <span data-ttu-id="5ba05-141">Im folgenden Codebeispiel wird veranschaulicht, wie eine Statusanzeige berechnen kann wie viel Speicherplatz während eines Kopiervorgangs verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="5ba05-141">The following code example illustrates how a progress bar can calculate how much disk space has been used during a copy operation.</span></span>  
  
     <span data-ttu-id="5ba05-142">Im folgenden Beispiel wenn jede Datei auf die Festplatte geschrieben werden sind die Statusanzeige und eine Bezeichnung entsprechend aktualisiert die Menge an Festplattenspeicher zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="5ba05-142">In the following example, as each file is written to the hard disk, the progress bar and label are updated to reflect the amount of hard-disk space available.</span></span> <span data-ttu-id="5ba05-143">Dieses Beispiel erfordert, dass das Formular enthält ein <xref:System.Windows.Forms.Label> Steuerelement und ein <xref:System.Windows.Forms.ProgressBar> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="5ba05-143">This example requires that your form has a <xref:System.Windows.Forms.Label> control and a <xref:System.Windows.Forms.ProgressBar> control.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5ba05-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5ba05-144">See also</span></span>

- <xref:System.Windows.Forms.ProgressBar>
- <xref:System.Windows.Forms.ToolStripProgressBar>
- [<span data-ttu-id="5ba05-145">Übersicht über das ProgressBar-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="5ba05-145">ProgressBar Control Overview</span></span>](progressbar-control-overview-windows-forms.md)
- [<span data-ttu-id="5ba05-146">ProgressBar-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="5ba05-146">ProgressBar Control</span></span>](progressbar-control-windows-forms.md)

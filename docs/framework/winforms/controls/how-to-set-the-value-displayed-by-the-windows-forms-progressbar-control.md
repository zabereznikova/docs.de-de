---
title: Festlegen des von ProgressBar Control angezeigten Werts
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ProgressBar control [Windows Forms], setting value displayed
- progress controls [Windows Forms], setting value displayed
ms.assetid: 0e5010ad-1e9a-4271-895e-5a3d24d37a26
ms.openlocfilehash: d295079a96ca19a4e4c98e113a3f3051c6403182
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141810"
---
# <a name="how-to-set-the-value-displayed-by-the-windows-forms-progressbar-control"></a><span data-ttu-id="a8768-102">Gewusst wie: Festlegen des vom ProgressBar-Steuerelement für Windows Forms angezeigten Werts</span><span class="sxs-lookup"><span data-stu-id="a8768-102">How to: Set the Value Displayed by the Windows Forms ProgressBar Control</span></span>
> [!IMPORTANT]
> <span data-ttu-id="a8768-103">Obwohl das <xref:System.Windows.Forms.ToolStripProgressBar>-Steuerelement das <xref:System.Windows.Forms.ProgressBar>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.ProgressBar>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.</span><span class="sxs-lookup"><span data-stu-id="a8768-103">The <xref:System.Windows.Forms.ToolStripProgressBar> control replaces and adds functionality to the <xref:System.Windows.Forms.ProgressBar> control; however, the <xref:System.Windows.Forms.ProgressBar> control is retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="a8768-104">Mit .NET Framework können Sie verschiedene Möglichkeiten zum <xref:System.Windows.Forms.ProgressBar> Anzeigen eines bestimmten Werts innerhalb des Steuerelements bieten.</span><span class="sxs-lookup"><span data-stu-id="a8768-104">The .NET Framework gives you several different ways to display a given value within the <xref:System.Windows.Forms.ProgressBar> control.</span></span> <span data-ttu-id="a8768-105">Welchen Ansatz Sie wählen, hängt von der anstehenden Aufgabe oder dem Problem ab, das Sie lösen.</span><span class="sxs-lookup"><span data-stu-id="a8768-105">Which approach you choose will depend on the task at hand or the problem you are solving.</span></span> <span data-ttu-id="a8768-106">Die folgende Tabelle zeigt die Ansätze, die Sie auswählen können.</span><span class="sxs-lookup"><span data-stu-id="a8768-106">The following table shows the approaches you can choose.</span></span>  
  
|<span data-ttu-id="a8768-107">Vorgehensweise</span><span class="sxs-lookup"><span data-stu-id="a8768-107">Approach</span></span>|<span data-ttu-id="a8768-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a8768-108">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="a8768-109">Legen Sie den <xref:System.Windows.Forms.ProgressBar> Wert des Steuerelements direkt fest.</span><span class="sxs-lookup"><span data-stu-id="a8768-109">Set the value of the <xref:System.Windows.Forms.ProgressBar> control directly.</span></span>|<span data-ttu-id="a8768-110">Dieser Ansatz ist nützlich für Aufgaben, bei denen Sie die Summe des gemessenen Elements kennen, z. B. das Lesen von Datensätzen aus einer Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="a8768-110">This approach is useful for tasks where you know the total of the item measured that will be involved, such as reading records from a data source.</span></span> <span data-ttu-id="a8768-111">Wenn Sie den Wert nur ein- oder zweimal festlegen müssen, ist dies eine einfache Möglichkeit.</span><span class="sxs-lookup"><span data-stu-id="a8768-111">Additionally, if you only need to set the value once or twice, this is an easy way to do it.</span></span> <span data-ttu-id="a8768-112">Verwenden Sie diesen Prozess schließlich, wenn Sie den wert verringern müssen, der im Fortschrittsbalken angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="a8768-112">Finally, use this process if you need to decrease the value displayed by the progress bar.</span></span>|  
|<span data-ttu-id="a8768-113">Erhöhen <xref:System.Windows.Forms.ProgressBar> Sie die Anzeige um einen festen Wert.</span><span class="sxs-lookup"><span data-stu-id="a8768-113">Increase the <xref:System.Windows.Forms.ProgressBar> display by a fixed value.</span></span>|<span data-ttu-id="a8768-114">Dieser Ansatz ist nützlich, wenn Sie eine einfache Anzahl zwischen dem Minimum und dem Maximum anzeigen, z. B. die verstrichene Zeit oder die Anzahl der Dateien, die aus einer bekannten Summe verarbeitet wurden.</span><span class="sxs-lookup"><span data-stu-id="a8768-114">This approach is useful when you are displaying a simple count between the minimum and maximum, such as elapsed time or the number of files that have been processed out of a known total.</span></span>|  
|<span data-ttu-id="a8768-115">Erhöhen <xref:System.Windows.Forms.ProgressBar> Sie die Anzeige um einen Wert, der variiert.</span><span class="sxs-lookup"><span data-stu-id="a8768-115">Increase the <xref:System.Windows.Forms.ProgressBar> display by a value that varies.</span></span>|<span data-ttu-id="a8768-116">Dieser Ansatz ist nützlich, wenn Sie den angezeigten Wert mehrmals in verschiedenen Beträgen ändern müssen.</span><span class="sxs-lookup"><span data-stu-id="a8768-116">This approach is useful when you need to change the displayed value a number of times in different amounts.</span></span> <span data-ttu-id="a8768-117">Ein Beispiel wäre das Anzeigen des Speicherplatzes, der beim Schreiben einer Reihe von Dateien auf die Festplatte verbraucht wird.</span><span class="sxs-lookup"><span data-stu-id="a8768-117">An example would be showing the amount of hard-disk space being consumed while writing a series of files to the disk.</span></span>|  
  
 <span data-ttu-id="a8768-118">Die direkteste Möglichkeit, den von einem Fortschrittsbalken <xref:System.Windows.Forms.ProgressBar.Value%2A> angezeigten Wert festzulegen, besteht darin, die Eigenschaft festzulegen.</span><span class="sxs-lookup"><span data-stu-id="a8768-118">The most direct way to set the value displayed by a progress bar is by setting the <xref:System.Windows.Forms.ProgressBar.Value%2A> property.</span></span> <span data-ttu-id="a8768-119">Dies kann entweder zur Entwurfszeit oder zur Laufzeit erfolgen.</span><span class="sxs-lookup"><span data-stu-id="a8768-119">This can be done either at design time or at run time.</span></span>  
  
### <a name="to-set-the-progressbar-value-directly"></a><span data-ttu-id="a8768-120">So legen Sie den ProgressBar-Wert direkt fest</span><span class="sxs-lookup"><span data-stu-id="a8768-120">To set the ProgressBar value directly</span></span>  
  
1. <span data-ttu-id="a8768-121">Legen <xref:System.Windows.Forms.ProgressBar> Sie die <xref:System.Windows.Forms.ProgressBar.Minimum%2A> <xref:System.Windows.Forms.ProgressBar.Maximum%2A> Werte und Werte des Steuerelements fest.</span><span class="sxs-lookup"><span data-stu-id="a8768-121">Set the <xref:System.Windows.Forms.ProgressBar> control's <xref:System.Windows.Forms.ProgressBar.Minimum%2A> and <xref:System.Windows.Forms.ProgressBar.Maximum%2A> values.</span></span>  
  
2. <span data-ttu-id="a8768-122">Legen Sie im Code <xref:System.Windows.Forms.ProgressBar.Value%2A> die Eigenschaft des Steuerelements auf einen Ganzzahlwert zwischen den von Ihnen festgelegten minimalen und maximalen Werten fest.</span><span class="sxs-lookup"><span data-stu-id="a8768-122">In code, set the control's <xref:System.Windows.Forms.ProgressBar.Value%2A> property to an integer value between the minimum and maximum values you have established.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="a8768-123">Wenn Sie <xref:System.Windows.Forms.ProgressBar.Value%2A> die Eigenschaft außerhalb der <xref:System.Windows.Forms.ProgressBar.Minimum%2A> <xref:System.Windows.Forms.ProgressBar.Maximum%2A> grenzen festlegen, die <xref:System.ArgumentException> durch die und Eigenschaften festgelegt wurden, löst das Steuerelement eine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="a8768-123">If you set the <xref:System.Windows.Forms.ProgressBar.Value%2A> property outside the boundaries established by the <xref:System.Windows.Forms.ProgressBar.Minimum%2A> and <xref:System.Windows.Forms.ProgressBar.Maximum%2A> properties, the control throws an <xref:System.ArgumentException> exception.</span></span>  
  
     <span data-ttu-id="a8768-124">Im folgenden Codebeispiel wird veranschaulicht, wie der Wert direkt festgelegt wird. <xref:System.Windows.Forms.ProgressBar></span><span class="sxs-lookup"><span data-stu-id="a8768-124">The following code example illustrates how to set the <xref:System.Windows.Forms.ProgressBar> value directly.</span></span> <span data-ttu-id="a8768-125">Der Code liest Datensätze aus einer Datenquelle und aktualisiert die Statusleiste und Beschriftung jedes Mal, wenn ein Datensatz gelesen wird.</span><span class="sxs-lookup"><span data-stu-id="a8768-125">The code reads records from a data source and updates the progress bar and label every time a data record is read.</span></span> <span data-ttu-id="a8768-126">In diesem Beispiel muss <xref:System.Windows.Forms.Label> das Formular <xref:System.Windows.Forms.ProgressBar> über ein Steuerelement, ein `CustomerRow` Steuerelement `FirstName` `LastName` und eine Datentabelle mit einer Zeile mit und Feldern verfügen.</span><span class="sxs-lookup"><span data-stu-id="a8768-126">This example requires that your form has a <xref:System.Windows.Forms.Label> control, a <xref:System.Windows.Forms.ProgressBar> control, and a data table with a row called `CustomerRow` with `FirstName` and `LastName` fields.</span></span>  
  
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
  
     Wenn Sie den Fortschritt anzeigen, der nach einem festen Intervall verläuft, können <xref:System.Windows.Forms.ProgressBar> Sie den Wert festlegen und dann eine Methode aufrufen, die den Wert des Steuerelements um dieses Intervall erhöht. <span data-ttu-id="a8768-128">Dies ist nützlich für Timer und andere Szenarien, in denen Sie den Fortschritt nicht als Prozentsatz des Ganzen messen.</span><span class="sxs-lookup"><span data-stu-id="a8768-128">This is useful for timers and other scenarios where you are not measuring progress as a percentage of the whole.</span></span>  
  
### <a name="to-increase-the-progress-bar-by-a-fixed-value"></a><span data-ttu-id="a8768-129">So erhöhen Sie den Fortschrittsbalken um einen festen Wert</span><span class="sxs-lookup"><span data-stu-id="a8768-129">To increase the progress bar by a fixed value</span></span>  
  
1. <span data-ttu-id="a8768-130">Legen <xref:System.Windows.Forms.ProgressBar> Sie die <xref:System.Windows.Forms.ProgressBar.Minimum%2A> <xref:System.Windows.Forms.ProgressBar.Maximum%2A> Werte und Werte des Steuerelements fest.</span><span class="sxs-lookup"><span data-stu-id="a8768-130">Set the <xref:System.Windows.Forms.ProgressBar> control's <xref:System.Windows.Forms.ProgressBar.Minimum%2A> and <xref:System.Windows.Forms.ProgressBar.Maximum%2A> values.</span></span>  
  
2. <span data-ttu-id="a8768-131">Legen Sie die <xref:System.Windows.Forms.ProgressBar.Step%2A> Eigenschaft des Steuerelements auf eine ganze Zahl fest, die den Betrag darstellt, um den angezeigten Wert des Fortschrittsbalkens zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="a8768-131">Set the control's <xref:System.Windows.Forms.ProgressBar.Step%2A> property to an integer representing the amount to increase the progress bar's displayed value.</span></span>  
  
3. <span data-ttu-id="a8768-132">Rufen <xref:System.Windows.Forms.ProgressBar.PerformStep%2A> Sie die Methode auf, um den <xref:System.Windows.Forms.ProgressBar.Step%2A> Wert zu ändern, der durch den in der Eigenschaft festgelegten Betrag angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="a8768-132">Call the <xref:System.Windows.Forms.ProgressBar.PerformStep%2A> method to change the value displayed by the amount set in the <xref:System.Windows.Forms.ProgressBar.Step%2A> property.</span></span>  
  
     <span data-ttu-id="a8768-133">Das folgende Codebeispiel veranschaulicht, wie eine Fortschrittsleiste die Anzahl der Dateien in einem Kopiervorgang verwalten kann.</span><span class="sxs-lookup"><span data-stu-id="a8768-133">The following code example illustrates how a progress bar can maintain a count of the files in a copy operation.</span></span>  
  
     <span data-ttu-id="a8768-134">Im folgenden Beispiel werden die Statusanzeige und die Bezeichnung aktualisiert, wenn jede Datei in den Arbeitsspeicher eingelesen wird, um die gelesenen Gesamtdateien widerzuspiegeln.</span><span class="sxs-lookup"><span data-stu-id="a8768-134">In the following example, as each file is read into memory, the progress bar and label are updated to reflect the total files read.</span></span> <span data-ttu-id="a8768-135">In diesem Beispiel muss <xref:System.Windows.Forms.Label> das Formular <xref:System.Windows.Forms.ProgressBar> über ein Steuerelement und ein Steuerelement verfügen.</span><span class="sxs-lookup"><span data-stu-id="a8768-135">This example requires that your form has a <xref:System.Windows.Forms.Label> control and a <xref:System.Windows.Forms.ProgressBar> control.</span></span>  
  
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
  
     Schließlich können Sie den Wert erhöhen, der durch einen Fortschrittsbalken angezeigt wird, sodass jede Erhöhung ein eindeutiger Betrag ist. <span data-ttu-id="a8768-137">Dies ist nützlich, wenn Sie eine Reihe von eindeutigen Vorgängen nachverfolgen, z. B. das Schreiben von Dateien unterschiedlicher Größe auf eine Festplatte oder das Messen des Fortschritts als Prozentsatz des Ganzen.</span><span class="sxs-lookup"><span data-stu-id="a8768-137">This is useful when you are keeping track of a series of unique operations, such as writing files of different sizes to a hard disk, or measuring progress as a percentage of the whole.</span></span>  
  
### <a name="to-increase-the-progress-bar-by-a-dynamic-value"></a><span data-ttu-id="a8768-138">So erhöhen Sie den Fortschrittsbalken um einen dynamischen Wert</span><span class="sxs-lookup"><span data-stu-id="a8768-138">To increase the progress bar by a dynamic value</span></span>  
  
1. <span data-ttu-id="a8768-139">Legen <xref:System.Windows.Forms.ProgressBar> Sie die <xref:System.Windows.Forms.ProgressBar.Minimum%2A> <xref:System.Windows.Forms.ProgressBar.Maximum%2A> Werte und Werte des Steuerelements fest.</span><span class="sxs-lookup"><span data-stu-id="a8768-139">Set the <xref:System.Windows.Forms.ProgressBar> control's <xref:System.Windows.Forms.ProgressBar.Minimum%2A> and <xref:System.Windows.Forms.ProgressBar.Maximum%2A> values.</span></span>  
  
2. <span data-ttu-id="a8768-140">Rufen <xref:System.Windows.Forms.ProgressBar.Increment%2A> Sie die Methode auf, um den Wert zu ändern, der von einer von Ihnen angegebenen Ganzzahl angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="a8768-140">Call the <xref:System.Windows.Forms.ProgressBar.Increment%2A> method to change the value displayed by an integer you specify.</span></span>  
  
     <span data-ttu-id="a8768-141">Das folgende Codebeispiel veranschaulicht, wie ein Fortschrittsbalken berechnen kann, wie viel Speicherplatz während eines Kopiervorgangs verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="a8768-141">The following code example illustrates how a progress bar can calculate how much disk space has been used during a copy operation.</span></span>  
  
     <span data-ttu-id="a8768-142">Im folgenden Beispiel werden die Statusanzeige und die Bezeichnung aktualisiert, um den verfügbaren Festplattenspeicher widerzuspiegeln, wenn jede Datei auf die Festplatte geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="a8768-142">In the following example, as each file is written to the hard disk, the progress bar and label are updated to reflect the amount of hard-disk space available.</span></span> <span data-ttu-id="a8768-143">In diesem Beispiel muss <xref:System.Windows.Forms.Label> das Formular <xref:System.Windows.Forms.ProgressBar> über ein Steuerelement und ein Steuerelement verfügen.</span><span class="sxs-lookup"><span data-stu-id="a8768-143">This example requires that your form has a <xref:System.Windows.Forms.Label> control and a <xref:System.Windows.Forms.ProgressBar> control.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a8768-144">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a8768-144">See also</span></span>

- <xref:System.Windows.Forms.ProgressBar>
- <xref:System.Windows.Forms.ToolStripProgressBar>
- [<span data-ttu-id="a8768-145">Übersicht über das ProgressBar-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="a8768-145">ProgressBar Control Overview</span></span>](progressbar-control-overview-windows-forms.md)
- [<span data-ttu-id="a8768-146">ProgressBar-Steuerung</span><span class="sxs-lookup"><span data-stu-id="a8768-146">ProgressBar Control</span></span>](progressbar-control-windows-forms.md)

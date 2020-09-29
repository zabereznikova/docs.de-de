---
title: 'Vorgehensweise: Erstellen einer Datei oder eines Ordners (C#-Programmierleitfaden)'
description: Erfahren Sie, wie Sie programmgesteuert eine Datei oder einen Ordner erstellen. Sie können einen Ordner, einen Unterordner und eine Datei im Unterordner erstellen und Daten in diese Datei schreiben.
ms.date: 07/20/2015
helpviewer_keywords:
- folders [C#]
- creating files [C#]
- files [C#]
- creating folders [C#]
ms.assetid: 4582ee2d-d72d-4687-bcb9-08d336c62c25
ms.openlocfilehash: 4d60b8c6c0f9d4ea66125374327f5e1ad2098694
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91167443"
---
# <a name="how-to-create-a-file-or-folder-c-programming-guide"></a><span data-ttu-id="0021d-104">Vorgehensweise: Erstellen einer Datei oder eines Ordners (C#-Programmierleitfaden)</span><span class="sxs-lookup"><span data-stu-id="0021d-104">How to create a file or folder (C# Programming Guide)</span></span>

<span data-ttu-id="0021d-105">Sie können einen Ordner auf dem Computer programmgesteuert erstellen, einen Unterordner erstellen, eine Datei im Unterordner erstellen und Daten in die Datei schreiben.</span><span class="sxs-lookup"><span data-stu-id="0021d-105">You can programmatically create a folder on your computer, create a subfolder, create a file in the subfolder, and write data to the file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0021d-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0021d-106">Example</span></span>  

 [!code-csharp[csFilesandFolders#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#10)]  
  
 <span data-ttu-id="0021d-107">Falls der Ordner bereits vorhanden ist, führt <xref:System.IO.Directory.CreateDirectory%2A> keine Aktion aus, und es wird keine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="0021d-107">If the folder already exists, <xref:System.IO.Directory.CreateDirectory%2A> does nothing, and no exception is thrown.</span></span> <span data-ttu-id="0021d-108">Allerdings wird mit <xref:System.IO.File.Create%2A?displayProperty=nameWithType> eine vorhandene Datei durch eine neue Datei ersetzt.</span><span class="sxs-lookup"><span data-stu-id="0021d-108">However, <xref:System.IO.File.Create%2A?displayProperty=nameWithType> replaces an existing file with a new file.</span></span> <span data-ttu-id="0021d-109">Im Beispiel wird eine `if`-`else`-Anweisung verwendet, um zu verhindern, dass eine vorhandene Datei ersetzt wird.</span><span class="sxs-lookup"><span data-stu-id="0021d-109">The example uses an `if`-`else` statement to prevent an existing file from being replaced.</span></span>  
  
 <span data-ttu-id="0021d-110">Wenn Sie die folgenden Änderungen im Beispiel vornehmen, können Sie, je nachdem, ob eine Datei mit einem bestimmten Namen bereits vorhanden ist, unterschiedliche Ergebnisse erzeugen.</span><span class="sxs-lookup"><span data-stu-id="0021d-110">By making the following changes in the example, you can specify different outcomes based on whether a file with a certain name already exists.</span></span> <span data-ttu-id="0021d-111">Wenn eine solche Datei nicht vorhanden ist, erstellt der Code sie.</span><span class="sxs-lookup"><span data-stu-id="0021d-111">If such a file doesn't exist, the code creates one.</span></span> <span data-ttu-id="0021d-112">Wenn eine solche Datei vorhanden ist, fügt der Code Daten an diese Datei an.</span><span class="sxs-lookup"><span data-stu-id="0021d-112">If such a file exists, the code appends data to that file.</span></span>  
  
- <span data-ttu-id="0021d-113">Geben Sie einen nicht zufälligen Dateinamen an.</span><span class="sxs-lookup"><span data-stu-id="0021d-113">Specify a non-random file name.</span></span>  
  
    ```csharp  
    // Comment out the following line.  
    //string fileName = System.IO.Path.GetRandomFileName();  
  
    // Replace that line with the following assignment.  
    string fileName = "MyNewFile.txt";  
    ```  
  
- <span data-ttu-id="0021d-114">Ersetzen Sie im folgenden Code die `if`-`else`-Anweisung durch die `using`-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="0021d-114">Replace the `if`-`else` statement with the `using` statement in the following code.</span></span>  
  
    ```csharp  
    using (System.IO.FileStream fs = new System.IO.FileStream(pathString, FileMode.Append))
    {  
        for (byte i = 0; i < 100; i++)  
        {  
            fs.WriteByte(i);  
        }  
    }  
    ```  
  
 <span data-ttu-id="0021d-115">Führen Sie das Beispiel mehrmals aus, um zu überprüfen, dass der Datei jedes Mal Daten hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="0021d-115">Run the example several times to verify that data is added to the file each time.</span></span>  
  
 <span data-ttu-id="0021d-116">Weitere `FileMode`-Werte, die Sie ausprobieren können, finden Sie unter <xref:System.IO.FileMode>.</span><span class="sxs-lookup"><span data-stu-id="0021d-116">For more `FileMode` values that you can try, see <xref:System.IO.FileMode>.</span></span>  
  
 <span data-ttu-id="0021d-117">Die folgenden Bedingungen können einen Ausnahmefehler verursachen:</span><span class="sxs-lookup"><span data-stu-id="0021d-117">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="0021d-118">Der Ordnername ist falsch formatiert.</span><span class="sxs-lookup"><span data-stu-id="0021d-118">The folder name is malformed.</span></span> <span data-ttu-id="0021d-119">Er enthält beispielsweise unzulässige Zeichen oder besteht nur aus Leerzeichen (<xref:System.ArgumentException>-Klasse).</span><span class="sxs-lookup"><span data-stu-id="0021d-119">For example, it contains illegal characters or is only white space (<xref:System.ArgumentException> class).</span></span> <span data-ttu-id="0021d-120">Verwenden Sie die <xref:System.IO.Path>-Klasse, um gültige Pfadnamen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="0021d-120">Use the <xref:System.IO.Path> class to create valid path names.</span></span>  
  
- <span data-ttu-id="0021d-121">Der übergeordnete Ordner des zu erstellenden Ordners ist schreibgeschützt (<xref:System.IO.IOException>-Klasse).</span><span class="sxs-lookup"><span data-stu-id="0021d-121">The parent folder of the folder to be created is read-only (<xref:System.IO.IOException> class).</span></span>  
  
- <span data-ttu-id="0021d-122">Der Ordnername ist `null` (<xref:System.ArgumentNullException>-Klasse).</span><span class="sxs-lookup"><span data-stu-id="0021d-122">The folder name is `null` (<xref:System.ArgumentNullException> class).</span></span>  
  
- <span data-ttu-id="0021d-123">Der Ordnername ist zu lang (<xref:System.IO.PathTooLongException>-Klasse).</span><span class="sxs-lookup"><span data-stu-id="0021d-123">The folder name is too long (<xref:System.IO.PathTooLongException> class).</span></span>  
  
- <span data-ttu-id="0021d-124">Der Ordnername besteht nur aus einem Doppelpunkt ":" (<xref:System.IO.PathTooLongException>-Klasse).</span><span class="sxs-lookup"><span data-stu-id="0021d-124">The folder name is only a colon, ":" (<xref:System.IO.PathTooLongException> class).</span></span>  
  
## <a name="net-security"></a><span data-ttu-id="0021d-125">.NET-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="0021d-125">.NET Security</span></span>  

 <span data-ttu-id="0021d-126">Eine Instanz der <xref:System.Security.SecurityException>-Klasse kann in nur teilweise vertrauenswürdigen Umgebungen ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="0021d-126">An instance of the <xref:System.Security.SecurityException> class may be thrown in partial-trust situations.</span></span>  
  
 <span data-ttu-id="0021d-127">Wenn Sie keine Berechtigung zum Erstellen des Ordners haben, wird in dem Beispiel eine Instanz der <xref:System.UnauthorizedAccessException>-Klasse ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="0021d-127">If you don't have permission to create the folder, the example throws an instance of the <xref:System.UnauthorizedAccessException> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0021d-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0021d-128">See also</span></span>

- <xref:System.IO?displayProperty=nameWithType>
- [<span data-ttu-id="0021d-129">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="0021d-129">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="0021d-130">Das Dateisystem und die Registrierung (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="0021d-130">File System and the Registry (C# Programming Guide)</span></span>](./index.md)

---
title: 'Gewusst wie: Erstellen einer Datei oder eines Ordners (C#-Programmierhandbuch)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- folders [C#]
- creating files [C#]
- files [C#]
- creating folders [C#]
ms.assetid: 4582ee2d-d72d-4687-bcb9-08d336c62c25
caps.latest.revision: 22
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 150190eeef829bd0431eeea7789025b9905553e3
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-create-a-file-or-folder-c-programming-guide"></a><span data-ttu-id="fbc3f-102">Gewusst wie: Erstellen einer Datei oder eines Ordners (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="fbc3f-102">How to: Create a File or Folder (C# Programming Guide)</span></span>
<span data-ttu-id="fbc3f-103">Sie können einen Ordner auf dem Computer programmgesteuert erstellen, einen Unterordner erstellen, eine Datei im Unterordner erstellen und Daten in die Datei schreiben.</span><span class="sxs-lookup"><span data-stu-id="fbc3f-103">You can programmatically create a folder on your computer, create a subfolder, create a file in the subfolder, and write data to the file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fbc3f-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fbc3f-104">Example</span></span>  
 <span data-ttu-id="fbc3f-105">[!code-cs[csFilesandFolders#10](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-create-a-file-or-folder_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="fbc3f-105">[!code-cs[csFilesandFolders#10](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-create-a-file-or-folder_1.cs)]</span></span>  
  
 <span data-ttu-id="fbc3f-106">Falls der Ordner bereits vorhanden ist, führt <xref:System.IO.Directory.CreateDirectory%2A> keine Aktion aus, und es wird keine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="fbc3f-106">If the folder already exists, <xref:System.IO.Directory.CreateDirectory%2A> does nothing, and no exception is thrown.</span></span> <span data-ttu-id="fbc3f-107">Allerdings wird mit <xref:System.IO.File.Create%2A?displayProperty=fullName> eine vorhandene Datei durch eine neue Datei ersetzt.</span><span class="sxs-lookup"><span data-stu-id="fbc3f-107">However, <xref:System.IO.File.Create%2A?displayProperty=fullName> replaces an existing file with a new file.</span></span> <span data-ttu-id="fbc3f-108">Im Beispiel wird eine `if`-`else`-Anweisung verwendet, um zu verhindern, dass eine vorhandene Datei ersetzt wird.</span><span class="sxs-lookup"><span data-stu-id="fbc3f-108">The example uses an `if`-`else` statement to prevent an existing file from being replaced.</span></span>  
  
 <span data-ttu-id="fbc3f-109">Wenn Sie die folgenden Änderungen im Beispiel vornehmen, können Sie, je nachdem, ob eine Datei mit einem bestimmten Namen bereits vorhanden ist, unterschiedliche Ergebnisse erzeugen.</span><span class="sxs-lookup"><span data-stu-id="fbc3f-109">By making the following changes in the example, you can specify different outcomes based on whether a file with a certain name already exists.</span></span> <span data-ttu-id="fbc3f-110">Wenn eine solche Datei nicht vorhanden ist, erstellt der Code sie.</span><span class="sxs-lookup"><span data-stu-id="fbc3f-110">If such a file doesn't exist, the code creates one.</span></span> <span data-ttu-id="fbc3f-111">Wenn eine solche Datei vorhanden ist, fügt der Code Daten an diese Datei an.</span><span class="sxs-lookup"><span data-stu-id="fbc3f-111">If such a file exists, the code appends data to that file.</span></span>  
  
-   <span data-ttu-id="fbc3f-112">Geben Sie einen nicht zufälligen Dateinamen an.</span><span class="sxs-lookup"><span data-stu-id="fbc3f-112">Specify a non-random file name.</span></span>  
  
    ```csharp  
    // Comment out the following line.  
    //string fileName = System.IO.Path.GetRandomFileName();  
  
    // Replace that line with the following assignment.  
    string fileName = "MyNewFile.txt";  
    ```  
  
-   <span data-ttu-id="fbc3f-113">Ersetzen Sie im folgenden Code die `if`-`else`-Anweisung durch die `using`-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="fbc3f-113">Replace the `if`-`else` statement with the `using` statement in the following code.</span></span>  
  
    ```csharp  
    using (System.IO.FileStream fs = new System.IO.FileStream(pathString, FileMode.Append))   
    {  
        for (byte i = 0; i < 100; i++)  
        {  
            fs.WriteByte(i);  
        }  
    }  
    ```  
  
 <span data-ttu-id="fbc3f-114">Führen Sie das Beispiel mehrmals aus, um zu überprüfen, dass der Datei jedes Mal Daten hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="fbc3f-114">Run the example several times to verify that data is added to the file each time.</span></span>  
  
 <span data-ttu-id="fbc3f-115">Weitere `FileMode`-Werte, die Sie ausprobieren können, finden Sie unter <xref:System.IO.FileMode>.</span><span class="sxs-lookup"><span data-stu-id="fbc3f-115">For more `FileMode` values that you can try, see <xref:System.IO.FileMode>.</span></span>  
  
 <span data-ttu-id="fbc3f-116">Die folgenden Bedingungen können einen Ausnahmefehler verursachen:</span><span class="sxs-lookup"><span data-stu-id="fbc3f-116">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="fbc3f-117">Der Ordnername ist falsch formatiert.</span><span class="sxs-lookup"><span data-stu-id="fbc3f-117">The folder name is malformed.</span></span> <span data-ttu-id="fbc3f-118">Er enthält beispielsweise unzulässige Zeichen oder besteht nur aus Leerzeichen (<xref:System.ArgumentException>-Klasse).</span><span class="sxs-lookup"><span data-stu-id="fbc3f-118">For example, it contains illegal characters or is only white space (<xref:System.ArgumentException> class).</span></span> <span data-ttu-id="fbc3f-119">Verwenden Sie die <xref:System.IO.Path>-Klasse, um gültige Pfadnamen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="fbc3f-119">Use the <xref:System.IO.Path> class to create valid path names.</span></span>  
  
-   <span data-ttu-id="fbc3f-120">Der übergeordnete Ordner des zu erstellenden Ordners ist schreibgeschützt (<xref:System.IO.IOException>-Klasse).</span><span class="sxs-lookup"><span data-stu-id="fbc3f-120">The parent folder of the folder to be created is read-only (<xref:System.IO.IOException> class).</span></span>  
  
-   <span data-ttu-id="fbc3f-121">Der Ordnername ist `null` (<xref:System.ArgumentNullException>-Klasse).</span><span class="sxs-lookup"><span data-stu-id="fbc3f-121">The folder name is `null` (<xref:System.ArgumentNullException> class).</span></span>  
  
-   <span data-ttu-id="fbc3f-122">Der Ordnername ist zu lang (<xref:System.IO.PathTooLongException>-Klasse).</span><span class="sxs-lookup"><span data-stu-id="fbc3f-122">The folder name is too long (<xref:System.IO.PathTooLongException> class).</span></span>  
  
-   <span data-ttu-id="fbc3f-123">Der Ordnername besteht nur aus einem Doppelpunkt ":" (<xref:System.IO.PathTooLongException>-Klasse).</span><span class="sxs-lookup"><span data-stu-id="fbc3f-123">The folder name is only a colon, ":" (<xref:System.IO.PathTooLongException> class).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="fbc3f-124">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="fbc3f-124">.NET Framework Security</span></span>  
 <span data-ttu-id="fbc3f-125">Eine Instanz der <xref:System.Security.SecurityException>-Klasse kann in nur teilweise vertrauenswürdigen Umgebungen ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="fbc3f-125">An instance of the <xref:System.Security.SecurityException> class may be thrown in partial-trust situations.</span></span>  
  
 <span data-ttu-id="fbc3f-126">Wenn Sie keine Berechtigung zum Erstellen des Ordners haben, wird in dem Beispiel eine Instanz der <xref:System.UnauthorizedAccessException>-Klasse ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="fbc3f-126">If you don’t have permission to create the folder, the example throws an instance of the <xref:System.UnauthorizedAccessException> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbc3f-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fbc3f-127">See Also</span></span>  
 <span data-ttu-id="fbc3f-128"><xref:System.IO?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="fbc3f-128"><xref:System.IO?displayProperty=fullName></span></span>   
 <span data-ttu-id="fbc3f-129">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="fbc3f-129">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="fbc3f-130">Das Dateisystem und die Registrierung (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="fbc3f-130">File System and the Registry (C# Programming Guide)</span></span>](../../../csharp/programming-guide/file-system/index.md)


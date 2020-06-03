---
title: 'Exemplarische Vorgehensweise: Beibehalten eines Objekts unter Verwendung von C#'
ms.date: 04/26/2018
ms.openlocfilehash: bbe239008629d687084af7e28a75fa68560ca0ab
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "82796066"
---
# <a name="walkthrough-persisting-an-object-using-c"></a><span data-ttu-id="3feaf-102">Exemplarische Vorgehensweise: Beibehalten eines Objekts unter Verwendung von C\#</span><span class="sxs-lookup"><span data-stu-id="3feaf-102">Walkthrough: persisting an object using C\#</span></span>

<span data-ttu-id="3feaf-103">Sie können die Serialisierung verwenden, um die Daten eines Objekts zwischen Instanzen beizubehalten. Dadurch können Sie Werte speichern und abrufen, wenn das Objekt das nächste Mal instanziiert wird.</span><span class="sxs-lookup"><span data-stu-id="3feaf-103">You can use serialization to persist an object's data between instances, which enables you to store values and retrieve them the next time that the object is instantiated.</span></span>

<span data-ttu-id="3feaf-104">In dieser exemplarischen Vorgehensweise erstellen Sie ein einfaches `Loan`-Objekt und behalten dessen Daten in einer Datei bei.</span><span class="sxs-lookup"><span data-stu-id="3feaf-104">In this walkthrough, you will create a basic `Loan` object and persist its data to a file.</span></span> <span data-ttu-id="3feaf-105">Anschließend rufen Sie die Daten aus der Datei ab, wenn Sie das Objekt neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="3feaf-105">You will then retrieve the data from the file when you re-create the object.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3feaf-106">Mit diesem Beispiel wird eine neue Datei erstellt, wenn diese noch nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="3feaf-106">This example creates a new file if the file does not already exist.</span></span> <span data-ttu-id="3feaf-107">Wenn eine Anwendung eine Datei erstellen muss, muss Sie über die `Create`-Berechtigung für den Ordner verfügen.</span><span class="sxs-lookup"><span data-stu-id="3feaf-107">If an application must create a file, that application must have `Create` permission for the folder.</span></span> <span data-ttu-id="3feaf-108">Berechtigungen werden mithilfe von Zugriffssteuerungslisten festgelegt.</span><span class="sxs-lookup"><span data-stu-id="3feaf-108">Permissions are set by using access control lists.</span></span> <span data-ttu-id="3feaf-109">Wenn die Datei bereits vorhanden ist, benötigt die Anwendung lediglich die Berechtigung `Write`, was einer geringeren Berechtigung entspricht.</span><span class="sxs-lookup"><span data-stu-id="3feaf-109">If the file already exists, the application needs only `Write` permission, a lesser permission.</span></span> <span data-ttu-id="3feaf-110">Aus Sicherheitsgründen sollte die Datei nach Möglichkeit erst im Verlauf der Bereitstellung erstellt werden. Außerdem sollte die `Read`-Berechtigung nur für eine einzelne Datei erteilt werden (anstatt „Create“-Berechtigungen für den gesamten Ordner zu gewähren).</span><span class="sxs-lookup"><span data-stu-id="3feaf-110">Where possible, it's more secure to create the file during deployment and only grant `Read` permissions to a single file (instead of Create permissions for a folder).</span></span> <span data-ttu-id="3feaf-111">Darüber hinaus ist es sicherer, Daten in Benutzerordner statt in Stammordner oder den Ordner „Programmdateien“ zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="3feaf-111">Also, it's more secure to write data to user folders than to the root folder or the Program Files folder.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3feaf-112">In diesem Beispiel werden Daten in einer Datei im Binärformat gespeichert.</span><span class="sxs-lookup"><span data-stu-id="3feaf-112">This example stores data in a binary format file.</span></span> <span data-ttu-id="3feaf-113">Diese Formate sollten nicht für sensible Daten wie Kennwörter oder Kreditkarteninformationen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3feaf-113">These formats should not be used for sensitive data, such as passwords or credit-card information.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3feaf-114">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="3feaf-114">Prerequisites</span></span>

- <span data-ttu-id="3feaf-115">Installieren Sie zum Erstellen und Ausführen von Builds das [.NET Core SDK](https://dotnet.microsoft.com/download).</span><span class="sxs-lookup"><span data-stu-id="3feaf-115">To build and run, install the [.NET Core SDK](https://dotnet.microsoft.com/download).</span></span>

- <span data-ttu-id="3feaf-116">Installieren Sie Ihren bevorzugten Code-Editor, wenn Sie dies nicht bereits erledigt haben.</span><span class="sxs-lookup"><span data-stu-id="3feaf-116">Install your favorite code editor, if you haven't already.</span></span>

> [!TIP]
> <span data-ttu-id="3feaf-117">Benötigen Sie einen Code-Editor?</span><span class="sxs-lookup"><span data-stu-id="3feaf-117">Need to install a code editor?</span></span> <span data-ttu-id="3feaf-118">Testen Sie [Visual Studio](https://visualstudio.com/downloads).</span><span class="sxs-lookup"><span data-stu-id="3feaf-118">Try [Visual Studio](https://visualstudio.com/downloads)!</span></span>

- <span data-ttu-id="3feaf-119">Dieses Beispiel erfordert C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="3feaf-119">The example requires C# 7.3.</span></span> <span data-ttu-id="3feaf-120">Siehe [Auswählen der C#-Sprachversion](../../../language-reference/configure-language-version.md).</span><span class="sxs-lookup"><span data-stu-id="3feaf-120">See [Select the C# language version](../../../language-reference/configure-language-version.md)</span></span>

<span data-ttu-id="3feaf-121">Sie können den Beispielcode online im [GitHub-Repository für .NET-Beispiele](https://github.com/dotnet/samples/tree/master/csharp/serialization) untersuchen.</span><span class="sxs-lookup"><span data-stu-id="3feaf-121">You can examine the sample code online [at the .NET samples GitHub repository](https://github.com/dotnet/samples/tree/master/csharp/serialization).</span></span>

## <a name="creating-the-loan-object"></a><span data-ttu-id="3feaf-122">Erstellen des Loan-Objekts</span><span class="sxs-lookup"><span data-stu-id="3feaf-122">Creating the loan object</span></span>

<span data-ttu-id="3feaf-123">Der erste Schritt ist das Erstellen einer `Loan`-Klasse und einer Konsolenanwendung, die die Klasse verwendet:</span><span class="sxs-lookup"><span data-stu-id="3feaf-123">The first step is to create a `Loan` class and a console application that uses the class:</span></span>

1. <span data-ttu-id="3feaf-124">Erstellen Sie eine neue Anwendung.</span><span class="sxs-lookup"><span data-stu-id="3feaf-124">Create a new application.</span></span> <span data-ttu-id="3feaf-125">Geben Sie `dotnet new console -o serialization` ein, um eine neue Konsolenanwendung in einem Unterverzeichnis mit dem Namen `serialization` zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="3feaf-125">Type `dotnet new console -o serialization` to create a new console application in a subdirectory named `serialization`.</span></span>
1. <span data-ttu-id="3feaf-126">Öffnen Sie die Anwendung in Ihrem Editor, und fügen Sie eine neue Klasse mit dem Namen `Loan.cs` hinzu.</span><span class="sxs-lookup"><span data-stu-id="3feaf-126">Open the application in your editor, and add a new class named `Loan.cs`.</span></span>
1. <span data-ttu-id="3feaf-127">Fügen Sie der `Loan`-Klasse den folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="3feaf-127">Add the following code to your `Loan` class:</span></span>

[!code-csharp[Loan class definition](../../../../../samples/snippets/csharp/serialization/Loan.cs#1)]

<span data-ttu-id="3feaf-128">Sie müssen ebenfalls eine einfache Anwendung erstellen, die die `Loan`-Klasse verwendet.</span><span class="sxs-lookup"><span data-stu-id="3feaf-128">You will also have to create an application that uses the `Loan` class.</span></span>

## <a name="serialize-the-loan-object"></a><span data-ttu-id="3feaf-129">Serialisieren des Loan-Objekts</span><span class="sxs-lookup"><span data-stu-id="3feaf-129">Serialize the loan object</span></span>

1. <span data-ttu-id="3feaf-130">Öffnen Sie `Program.cs`.</span><span class="sxs-lookup"><span data-stu-id="3feaf-130">Open `Program.cs`.</span></span> <span data-ttu-id="3feaf-131">Fügen Sie den folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="3feaf-131">Add the following code:</span></span>

[!code-csharp[Create a loan object](../../../../../samples/snippets/csharp/serialization/Program.cs#1)]

<span data-ttu-id="3feaf-132">Fügen Sie für das `PropertyChanged`-Ereignis einen Ereignishandler und einige Zeilen hinzu, um das `Loan`-Objekt zu bearbeiten und die Änderungen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="3feaf-132">Add an event handler for the `PropertyChanged` event, and a few lines to modify the `Loan` object and display the changes.</span></span> <span data-ttu-id="3feaf-133">Im folgenden Code können Sie die Änderungen sehen:</span><span class="sxs-lookup"><span data-stu-id="3feaf-133">You can see the additions in the following code:</span></span>

[!code-csharp[Listening for the PropertyChanged event](../../../../../samples/snippets/csharp/serialization/Program.cs#2)]

<span data-ttu-id="3feaf-134">Zu diesem Zeitpunkt können Sie den Code ausführen und die aktuelle Ausgabe sehen:</span><span class="sxs-lookup"><span data-stu-id="3feaf-134">At this point, you can run the code, and see the current output:</span></span>

```console
New customer value: Henry Clay
7.5
7.1
```

<span data-ttu-id="3feaf-135">Wenn Sie diese Anwendung wiederholt ausführen, werden immer dieselben Werte geschrieben.</span><span class="sxs-lookup"><span data-stu-id="3feaf-135">Running this application repeatedly always writes the same values.</span></span> <span data-ttu-id="3feaf-136">Jedes Mal, wenn Sie das Programm ausführen, wird ein neues Loan-Objekt erstellt.</span><span class="sxs-lookup"><span data-stu-id="3feaf-136">A new Loan object is created every time you run the program.</span></span> <span data-ttu-id="3feaf-137">In der Praxis ändern sich Zinssätze regelmäßig, aber nicht unbedingt jedes Mal wenn die Anwendung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="3feaf-137">In the real world, interest rates change periodically, but not necessarily every time that the application is run.</span></span> <span data-ttu-id="3feaf-138">Mithilfe von Serialisierungscode speichern Sie die aktuellsten Zinssätze zwischen den einzelnen Anwendungsinstanzen.</span><span class="sxs-lookup"><span data-stu-id="3feaf-138">Serialization code means you preserve the most recent interest rate between instances of the application.</span></span> <span data-ttu-id="3feaf-139">Im nächsten Schritt werden Sie durch Hinzufügen von Serialisierung zur Loan-Klasse genau das tun.</span><span class="sxs-lookup"><span data-stu-id="3feaf-139">In the next step, you will do just that by adding serialization to the Loan class.</span></span>

## <a name="using-serialization-to-persist-the-object"></a><span data-ttu-id="3feaf-140">Verwenden von Serialisierung zum Beibehalten des Objekts</span><span class="sxs-lookup"><span data-stu-id="3feaf-140">Using Serialization to Persist the Object</span></span>

<span data-ttu-id="3feaf-141">Sie müssen die Klasse zuerst mit dem Attribut `Serializable` markieren, um die Werte für die Loan-Klasse beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="3feaf-141">In order to persist the values for the Loan class, you must first mark the class with the `Serializable` attribute.</span></span> <span data-ttu-id="3feaf-142">Fügen Sie den folgenden Code oberhalb der Definition der Loan-Klasse hinzu.</span><span class="sxs-lookup"><span data-stu-id="3feaf-142">Add the following code above the Loan class definition:</span></span>

[!code-csharp[Loan class definition](../../../../../samples/snippets/csharp/serialization/Loan.cs#2)]

<span data-ttu-id="3feaf-143">Der Compiler wird vom Attribut <xref:System.SerializableAttribute> darüber informiert, dass der Inhalt der Klasse in einer Datei beibehalten werden kann.</span><span class="sxs-lookup"><span data-stu-id="3feaf-143">The <xref:System.SerializableAttribute> tells the compiler that everything in the class can be persisted to a file.</span></span> <span data-ttu-id="3feaf-144">Da das `PropertyChanged`-Ereignis keinen Teil des Objektgraphen darstellt, der gespeichert werden sollte, sollte es nicht serialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="3feaf-144">Because the `PropertyChanged` event does not represent part of the object graph that should be stored, it should not be serialized.</span></span> <span data-ttu-id="3feaf-145">Bei einer Serialisierung würden alle Objekte serialisiert werden, die diesem Ereignis zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="3feaf-145">Doing so would serialize all objects that are attached to that event.</span></span> <span data-ttu-id="3feaf-146">Sie können das <xref:System.NonSerializedAttribute>-Attribut zu der Felddeklaration für den Ereignishandler `PropertyChanged` hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="3feaf-146">You can add the <xref:System.NonSerializedAttribute> to the field declaration for the `PropertyChanged` event handler.</span></span>

[!code-csharp[Disable serialization for the event handler](../../../../../samples/snippets/csharp/serialization/Loan.cs#3)]

<span data-ttu-id="3feaf-147">Ab C# 7.3 können Sie Attribute an das Unterstützungsfeld einer automatisch implementierten Eigenschaft unter Verwendung des Zielwerts `field` anfügen.</span><span class="sxs-lookup"><span data-stu-id="3feaf-147">Beginning with C# 7.3, you can attach attributes to the backing field of an auto-implemented property using the `field` target value.</span></span> <span data-ttu-id="3feaf-148">Über den folgenden Code fügen Sie eine `TimeLastLoaded`-Eigenschaft hinzu und markieren diese als „nicht serialisierbar“:</span><span class="sxs-lookup"><span data-stu-id="3feaf-148">The following code adds a `TimeLastLoaded` property and marks it as not serializable:</span></span>

[!code-csharp[Disable serialization for an auto-implemented property](../../../../../samples/snippets/csharp/serialization/Loan.cs#4)]

<span data-ttu-id="3feaf-149">Fügen Sie als nächstes den Serialisierungscode zur LoanApp-Anwendung hinzu.</span><span class="sxs-lookup"><span data-stu-id="3feaf-149">The next step is to add the serialization code to the LoanApp application.</span></span> <span data-ttu-id="3feaf-150">Um die Klasse zu serialisieren und in eine Datei zu schreiben, verwenden Sie die Namespaces <xref:System.IO> und <xref:System.Runtime.Serialization.Formatters.Binary>.</span><span class="sxs-lookup"><span data-stu-id="3feaf-150">In order to serialize the class and write it to a file, you use the <xref:System.IO> and <xref:System.Runtime.Serialization.Formatters.Binary> namespaces.</span></span> <span data-ttu-id="3feaf-151">Sie können wie im folgenden Codebeispiel dargestellt Verweise zu den notwendigen Namespaces hinzufügen, damit Sie die vollqualifizierten Namen nicht eingeben müssen:</span><span class="sxs-lookup"><span data-stu-id="3feaf-151">To avoid typing the fully qualified names, you can add references to the necessary namespaces as shown in the following code:</span></span>

[!code-csharp[Adding namespaces for serialization](../../../../../samples/snippets/csharp/serialization/Program.cs#3)]

<span data-ttu-id="3feaf-152">Fügen Sie als nächstes Code hinzu, um das Objekt aus der Datei zu deserialisieren wenn das Objekt erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="3feaf-152">The next step is to add code to deserialize the object from the file when the object is created.</span></span> <span data-ttu-id="3feaf-153">Fügen Sie wie im folgenden Codebeispiel dargestellt eine Konstante zur Klasse für den Dateinamen der serialisierten Daten hinzu:</span><span class="sxs-lookup"><span data-stu-id="3feaf-153">Add a constant to the class for the serialized data's file name as shown in the following code:</span></span>

[!code-csharp[Define the name of the saved file](../../../../../samples/snippets/csharp/serialization/Program.cs#4)]

<span data-ttu-id="3feaf-154">Fügen Sie dann im Anschluss an die Zeile, die das `TestLoan`-Objekt erstellt, den folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="3feaf-154">Next, add the following code after the line that creates the `TestLoan` object:</span></span>

[!code-csharp[Read from a file if it exists](../../../../../samples/snippets/csharp/serialization/Program.cs#5)]

<span data-ttu-id="3feaf-155">Sie müssen erst sicherstellen, ob die Datei vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="3feaf-155">You first must check that the file exists.</span></span> <span data-ttu-id="3feaf-156">Wenn sie vorhanden ist, erstellen Sie eine <xref:System.IO.Stream>-Klasse zum Lesen der Binärdatei und eine <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>-Klasse zum Übersetzen der Datei.</span><span class="sxs-lookup"><span data-stu-id="3feaf-156">If it exists, create a <xref:System.IO.Stream> class to read the binary file and a <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> class to translate the file.</span></span> <span data-ttu-id="3feaf-157">Sie müssen ebenfalls vom Streamtyp in den Loan-Objekttyp konvertieren.</span><span class="sxs-lookup"><span data-stu-id="3feaf-157">You also need to convert from the stream type to the Loan object type.</span></span>

<span data-ttu-id="3feaf-158">Als nächstes müssen Sie Code hinzufügen, um die Klasse in eine Datei zu serialisieren.</span><span class="sxs-lookup"><span data-stu-id="3feaf-158">Next you must add code to serialize the class to a file.</span></span> <span data-ttu-id="3feaf-159">Fügen Sie dem vorhandenen Code den folgenden Code in der `Main`-Methode hinzu:</span><span class="sxs-lookup"><span data-stu-id="3feaf-159">Add the following code after the existing code in the `Main` method:</span></span>

[!code-csharp[Save the existing Loan object](../../../../../samples/snippets/csharp/serialization/Program.cs#6)]

<span data-ttu-id="3feaf-160">Nun können Sie die Anwendung erneut erstellen und ausführen.</span><span class="sxs-lookup"><span data-stu-id="3feaf-160">At this point, you can again build and run the application.</span></span> <span data-ttu-id="3feaf-161">Beachten Sie, dass die Zinssätze bei der ersten Ausführung bei 7,5 beginnen und dann in 7,1 umgewandelt werden.</span><span class="sxs-lookup"><span data-stu-id="3feaf-161">The first time it runs, notice that the interest rates starts at 7.5, and then changes to 7.1.</span></span> <span data-ttu-id="3feaf-162">Schließen Sie die Anwendung, und führen Sie sie dann erneut aus.</span><span class="sxs-lookup"><span data-stu-id="3feaf-162">Close the application and then run it again.</span></span> <span data-ttu-id="3feaf-163">Die Anwendung druckt dann die Meldung aus, die sie aus der gespeicherten Datei gelesen hat. Der Zinssatz liegt dann sogar vor dem Code, der diese ändert, bei 7,1.</span><span class="sxs-lookup"><span data-stu-id="3feaf-163">Now, the application prints the message that it has read the saved file, and the interest rate is 7.1 even before the code that changes it.</span></span>

## <a name="see-also"></a><span data-ttu-id="3feaf-164">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3feaf-164">See also</span></span>

- [<span data-ttu-id="3feaf-165">Serialisierung (C#)</span><span class="sxs-lookup"><span data-stu-id="3feaf-165">Serialization (C#)</span></span>](index.md)
- [<span data-ttu-id="3feaf-166">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="3feaf-166">C# Programming Guide</span></span>](../../index.md)

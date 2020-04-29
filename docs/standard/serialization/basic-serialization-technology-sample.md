---
title: Technologiebeispiel für einfache Serialisierung
ms.date: 03/30/2017
ms.assetid: 9d824e16-08d1-4a36-bc7f-2388c1f75f34
ms.openlocfilehash: e5dcc9ec7cf6f996c97262b14020552286c530da
ms.sourcegitcommit: da2dd2772fcf32b44eb18b1cbe8affd17b1753c9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/27/2019
ms.locfileid: "71353140"
---
# <a name="basic-serialization-technology-sample"></a><span data-ttu-id="b2788-102">Technologiebeispiel für einfache Serialisierung</span><span class="sxs-lookup"><span data-stu-id="b2788-102">Basic Serialization Technology Sample</span></span>

[<span data-ttu-id="b2788-103">Beispiel herunterladen</span><span class="sxs-lookup"><span data-stu-id="b2788-103">Download sample</span></span>](https://download.microsoft.com/download/4/7/B/47B2164C-E780-4B10-8DE4-2CB5B886E0A6/Technologies/Serialization/Runtime%20Serialization/Basic.zip.exe)

<span data-ttu-id="b2788-104">Dieses Beispiel zeigt, wie die Common Language Runtime ein Objektdiagramm im Speicher in einen Datenstream serialisieren kann.</span><span class="sxs-lookup"><span data-stu-id="b2788-104">This sample demonstrates the common language runtime's ability to serialize an object graph in memory to a stream.</span></span> <span data-ttu-id="b2788-105">In diesem Beispiel kann entweder <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> oder <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> für die Serialisierung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b2788-105">This sample can use either the <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> or the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> for serialization.</span></span> <span data-ttu-id="b2788-106">Eine mit Daten gefüllte verknüpfte Liste wird in einen Dateistream serialisiert bzw. aus diesem deserialisiert.</span><span class="sxs-lookup"><span data-stu-id="b2788-106">A linked list, filled with data, is serialized or deserialized to or from a file stream.</span></span> <span data-ttu-id="b2788-107">In beiden Fällen wird die Liste mit den Ergebnissen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b2788-107">In either case the list is displayed so that you can see the results.</span></span> <span data-ttu-id="b2788-108">Die verknüpfte Liste ist vom Typ `LinkedList`, einem durch dieses Beispiel definierten Typ.</span><span class="sxs-lookup"><span data-stu-id="b2788-108">The linked list is of type `LinkedList`, a type defined by this sample.</span></span>

<span data-ttu-id="b2788-109">Weitere Informationen zur Serialisierung finden Sie in den Kommentaren der Quellcodedateien und der Datei "build.proj".</span><span class="sxs-lookup"><span data-stu-id="b2788-109">Review comments in the source code and build.proj files for more information on serialization.</span></span>

### <a name="to-build-the-sample-using-the-command-prompt"></a><span data-ttu-id="b2788-110">So erstellen Sie das Beispiel mithilfe der Eingabeaufforderung</span><span class="sxs-lookup"><span data-stu-id="b2788-110">To build the sample using the Command Prompt</span></span>

1. <span data-ttu-id="b2788-111">Navigieren Sie mithilfe der Eingabeaufforderung zu einem der sprachspezifischen Unterverzeichnisse unter dem Verzeichnis "Technologies\Serialization\Runtime Serialization\Basic".</span><span class="sxs-lookup"><span data-stu-id="b2788-111">Navigate to one of the language-specific subdirectories under the Technologies\Serialization\Runtime Serialization\Basic directory, using the command prompt.</span></span>

2. <span data-ttu-id="b2788-112">Geben Sie je nach verwendeter Programmiersprache **msbuild SerializationCS.sln**, **msbuild SerializationJSL.sln** oder **msbuild SerializationVB.sln** in der Befehlszeile ein.</span><span class="sxs-lookup"><span data-stu-id="b2788-112">Type **msbuild SerializationCS.sln**, **msbuild SerializationJSL.sln** or **msbuild SerializationVB.sln**, depending on your choice of programming language, at the command line.</span></span>

### <a name="to-build-the-sample-using-visual-studio"></a><span data-ttu-id="b2788-113">So erstellen Sie das Beispiel mithilfe von Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b2788-113">To build the sample using Visual Studio</span></span>

1. <span data-ttu-id="b2788-114">Öffnen Sie den Datei-Explorer, und navigieren Sie zu einem der sprachspezifischen Unterverzeichnisse für das Beispiel.</span><span class="sxs-lookup"><span data-stu-id="b2788-114">Open File Explorer and navigate to one of the language-specific subdirectories for the sample.</span></span>

2. <span data-ttu-id="b2788-115">Doppelklicken Sie je nach verwendeter Programmiersprache auf das Symbol für die Datei SerializationCS.sln, SerializationJSL.sln oder SerializationVB.sln, um die Datei in Visual Studio zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="b2788-115">Double-click the icon for the SerializationCS.sln, SerializationJSL.sln or SerializationVB.sln file, depending on your choice of programming language, to open the file in Visual Studio.</span></span>

3. <span data-ttu-id="b2788-116">Wählen Sie im Menü **Erstellen** die Option **Projektmappe erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="b2788-116">In the **Build** menu, select **Build Solution**.</span></span>

 <span data-ttu-id="b2788-117">Die Beispielanwendung wird im Standardunterverzeichnis \bin oder \bin\Debug erstellt.</span><span class="sxs-lookup"><span data-stu-id="b2788-117">The sample application will be built in the default \bin or \bin\Debug subdirectory.</span></span>

### <a name="to-run-the-sample"></a><span data-ttu-id="b2788-118">So führen Sie das Beispiel aus</span><span class="sxs-lookup"><span data-stu-id="b2788-118">To run the sample</span></span>

1. <span data-ttu-id="b2788-119">Navigieren Sie zu dem Verzeichnis, das die erstellte ausführbare Datei enthält.</span><span class="sxs-lookup"><span data-stu-id="b2788-119">Navigate to the directory containing the built executable.</span></span>

2. <span data-ttu-id="b2788-120">Geben Sie **Serialization.exe** zusammen mit den gewünschten Parameterwerten in der Befehlszeile ein.</span><span class="sxs-lookup"><span data-stu-id="b2788-120">Type **Serialization.exe**, along with the parameter values you desire, at the command line.</span></span>

  > [!NOTE]
  > <span data-ttu-id="b2788-121">In diesem Beispiel wird eine Konsolenanwendung erstellt.</span><span class="sxs-lookup"><span data-stu-id="b2788-121">This sample builds a console application.</span></span> <span data-ttu-id="b2788-122">Sie müssen es über die Eingabeaufforderung starten, um die Ausgabe anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="b2788-122">You must launch it using the command prompt in order to view its output.</span></span>

## <a name="remarks"></a><span data-ttu-id="b2788-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b2788-123">Remarks</span></span>

<span data-ttu-id="b2788-124">Die Beispielanwendung akzeptiert Befehlszeilenparameter, die angeben, welcher Test durchgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="b2788-124">The sample application accepts command line parameters indicating which test you would like to execute.</span></span> <span data-ttu-id="b2788-125">Verwenden Sie die **sx Test.xml 10**-Parameter, um eine Liste mit 10 Knoten mithilfe der SOAP-Formatierung in eine Datei mit dem Namen **Test.xml** zu serialisieren.</span><span class="sxs-lookup"><span data-stu-id="b2788-125">To serialize a 10-node list to a file named **Test.xml** using the SOAP formatter, use the parameters **sx Test.xml 10**.</span></span>

<span data-ttu-id="b2788-126">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b2788-126">For Example:</span></span>

```console
Serialize.exe -sx Test.xml 10
```

<span data-ttu-id="b2788-127">Verwenden Sie die **dx Test.xml**-Parameter, um die Datei **Test.xml** aus dem vorherigen Beispiel zu deserialisieren.</span><span class="sxs-lookup"><span data-stu-id="b2788-127">To deserialize the **Test.xml** file from the previous example, use the parameters **dx Test.xml**.</span></span>

<span data-ttu-id="b2788-128">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b2788-128">For Example:</span></span>

```console
Serialize.exe -dx Test.xml
```

<span data-ttu-id="b2788-129">In den beiden oben aufgeführten Beispielen bedeutet das "x" im Befehlszeilenschalter, dass die XML-SOAP-Serialisierung durchgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="b2788-129">In the two examples above, the "x" in the command line switch indicates that you want XML SOAP serialization.</span></span> <span data-ttu-id="b2788-130">Verwenden Sie "b", um die binäre Serialisierung durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="b2788-130">You can use "b" in its place to use binary serialization.</span></span> <span data-ttu-id="b2788-131">Wenn die Serialisierung mit einer großen Anzahl an Knoten durchgeführt werden soll, sollten Sie die Konsolenausgabe in eine Datei umleiten.</span><span class="sxs-lookup"><span data-stu-id="b2788-131">If you wish to try serialization with a very large number of nodes, you might want to redirect the console output to a file.</span></span>

<span data-ttu-id="b2788-132">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b2788-132">For Example:</span></span>

```console
Serialize.exe -sb Test.bin 10000 >somefile.txt
```

<span data-ttu-id="b2788-133">In der folgenden Aufzählung werden die in diesem Beispiel verwendeten Klassen und Technologien kurz beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b2788-133">The following bullets briefly describe the classes and technologies used by this sample.</span></span>

- <span data-ttu-id="b2788-134">Laufzeitserialisierung</span><span class="sxs-lookup"><span data-stu-id="b2788-134">Runtime Serialization</span></span>

  - <span data-ttu-id="b2788-135"><xref:System.Runtime.Serialization.IFormatter> Wird verwendet, um auf ein <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>-Objekt oder ein <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>-Objekt zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="b2788-135"><xref:System.Runtime.Serialization.IFormatter> Used to refer to either a <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> or a <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> object.</span></span>

  - <span data-ttu-id="b2788-136"><xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> Wird verwendet, um eine verknüpfte Liste in einen Stream in einem binären Format zu serialisieren.</span><span class="sxs-lookup"><span data-stu-id="b2788-136"><xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> Used to serialize a linked list to a stream in a binary format.</span></span> <span data-ttu-id="b2788-137">Die Binärformatierung verwendet ein Format, das nur der <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>-Typ versteht.</span><span class="sxs-lookup"><span data-stu-id="b2788-137">The binary formatter uses a format that only the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> type understands.</span></span> <span data-ttu-id="b2788-138">Die Daten sind jedoch präzise.</span><span class="sxs-lookup"><span data-stu-id="b2788-138">However, the data is concise.</span></span>

  - <span data-ttu-id="b2788-139"><xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> Wird verwendet, um eine verknüpfte Liste in einen Stream im SOAP-Format zu serialisieren.</span><span class="sxs-lookup"><span data-stu-id="b2788-139"><xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> Used to serialize a linked list to a stream in the SOAP format.</span></span> <span data-ttu-id="b2788-140">SOAP ist ein Standardformat.</span><span class="sxs-lookup"><span data-stu-id="b2788-140">SOAP is a standard format.</span></span>

- <span data-ttu-id="b2788-141">Stream-E/A</span><span class="sxs-lookup"><span data-stu-id="b2788-141">Stream I/O</span></span>

  - <span data-ttu-id="b2788-142"><xref:System.IO.Stream> Wird zum Serialisieren und Deserialisieren verwendet.</span><span class="sxs-lookup"><span data-stu-id="b2788-142"><xref:System.IO.Stream> Used to serialize and deserialize.</span></span> <span data-ttu-id="b2788-143">Bei dem in diesem Beispiel verwendeten speziellen Streamtyp handelt es sich um den <xref:System.IO.FileStream>-Typ.</span><span class="sxs-lookup"><span data-stu-id="b2788-143">The specific stream type used in this sample is the <xref:System.IO.FileStream> type.</span></span> <span data-ttu-id="b2788-144">Die Serialisierung kann jedoch mit einem beliebigen aus <xref:System.IO.Stream> abgeleitetet Typ durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="b2788-144">However, serialization can be used with any type derived from <xref:System.IO.Stream>.</span></span>

  - <span data-ttu-id="b2788-145"><xref:System.IO.File> Wird zum Erstellen von <xref:System.IO.FileStream>-Objekten zum Lesen und Erstellen von Dateien auf einem Datenträger verwendet.</span><span class="sxs-lookup"><span data-stu-id="b2788-145"><xref:System.IO.File> Used to create <xref:System.IO.FileStream> objects for reading and creating files on disk.</span></span>

  - <span data-ttu-id="b2788-146"><xref:System.IO.FileStream> Wird zum Serialisieren und Deserialisieren verknüpfter Listen verwendet.</span><span class="sxs-lookup"><span data-stu-id="b2788-146"><xref:System.IO.FileStream> Used to serialize and deserialize linked lists.</span></span>

## <a name="see-also"></a><span data-ttu-id="b2788-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b2788-147">See also</span></span>

- <xref:System.IO>
- <xref:System.IO.File>
- <xref:System.IO.FileStream>
- <xref:System.IO.Stream>
- <xref:System.Random>
- <xref:System.Runtime.Serialization>
- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>
- <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>
- <xref:System.Runtime.Serialization.IFormatter>
- <xref:System.SerializableAttribute>
- <xref:System.Xml.Serialization>
- [<span data-ttu-id="b2788-148">Einfache Serialisierung</span><span class="sxs-lookup"><span data-stu-id="b2788-148">Basic Serialization</span></span>](../../../docs/standard/serialization/basic-serialization.md)
- [<span data-ttu-id="b2788-149">Binäre Serialisierung</span><span class="sxs-lookup"><span data-stu-id="b2788-149">Binary Serialization</span></span>](../../../docs/standard/serialization/binary-serialization.md)
- [<span data-ttu-id="b2788-150">Steuern der XML-Serialisierung mit Attributen</span><span class="sxs-lookup"><span data-stu-id="b2788-150">Controlling XML Serialization Using Attributes</span></span>](../../../docs/standard/serialization/controlling-xml-serialization-using-attributes.md)
- [<span data-ttu-id="b2788-151">Einführung in die XML-Serialisierung</span><span class="sxs-lookup"><span data-stu-id="b2788-151">Introducing XML Serialization</span></span>](../../../docs/standard/serialization/introducing-xml-serialization.md)
- [<span data-ttu-id="b2788-152">Serialisierung</span><span class="sxs-lookup"><span data-stu-id="b2788-152">Serialization</span></span>](../../../docs/standard/serialization/index.md)
- [<span data-ttu-id="b2788-153">XML- und SOAP-Serialisierung</span><span class="sxs-lookup"><span data-stu-id="b2788-153">XML and SOAP Serialization</span></span>](../../../docs/standard/serialization/xml-and-soap-serialization.md)

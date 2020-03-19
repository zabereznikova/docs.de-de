---
title: SqlMetal.exe (Tool zur Codegenerierung)
ms.date: 03/30/2017
helpviewer_keywords:
- SQLMetal [LINQ to SQL]
- code generation tool
- SQLMetal.exe
- LINQ to SQL, serialization
- LINQ to SQL, DBML files
- LINQ to SQL, SQLMetal
ms.assetid: 819e5a96-7646-4fdb-b14b-fe31221b0614
ms.openlocfilehash: d5b4c2b59b585b3d3a3584ef9055e70c9d998e85
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "71044079"
---
# <a name="sqlmetalexe-code-generation-tool"></a><span data-ttu-id="5427f-102">SqlMetal.exe (Tool zur Codegenerierung)</span><span class="sxs-lookup"><span data-stu-id="5427f-102">SqlMetal.exe (Code Generation Tool)</span></span>
<span data-ttu-id="5427f-103">Das SqlMetal-Befehlszeilentool generiert Code und Zuordnungen für die [!INCLUDE[vbtecdlinq](../../../includes/vbtecdlinq-md.md)]-Komponente von .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5427f-103">The SqlMetal command-line tool generates code and mapping for the [!INCLUDE[vbtecdlinq](../../../includes/vbtecdlinq-md.md)] component of the .NET Framework.</span></span> <span data-ttu-id="5427f-104">Durch Anwenden der später in diesem Thema behandelten Optionen können Sie SqlMetal anweisen, mehrere verschiedene Aktionen wie etwa die folgenden auszuführen:</span><span class="sxs-lookup"><span data-stu-id="5427f-104">By applying options that appear later in this topic, you can instruct SqlMetal to perform several different actions that include the following:</span></span>  
  
- <span data-ttu-id="5427f-105">Generieren von Quellcode und Zuordnungsattributen oder einer Zuordnungsdatei von einer Datenbank aus</span><span class="sxs-lookup"><span data-stu-id="5427f-105">From a database, generate source code and mapping attributes or a mapping file.</span></span>  
  
- <span data-ttu-id="5427f-106">Generieren einer DBML-Datei (Intermediate Database Markup Language) zum Anpassen von einer Datenbank aus</span><span class="sxs-lookup"><span data-stu-id="5427f-106">From a database, generate an intermediate database markup language (.dbml) file for customization.</span></span>  
  
- <span data-ttu-id="5427f-107">Generieren von Code und Zuordnungsattributen oder einer Zuordnungsdatei von einer DBML-Datei aus</span><span class="sxs-lookup"><span data-stu-id="5427f-107">From a .dbml file, generate code and mapping attributes or a mapping file.</span></span>  
  
 <span data-ttu-id="5427f-108">Dieses Tool wird automatisch mit Visual Studio installiert.</span><span class="sxs-lookup"><span data-stu-id="5427f-108">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="5427f-109">Standardmäßig befindet sich die Datei unter " `drive`:\Programme\Microsoft SDKs\Windows\v`n.nn`\bin".</span><span class="sxs-lookup"><span data-stu-id="5427f-109">By default, the file is located at `drive`:\Program Files\Microsoft SDKs\Windows\v`n.nn`\bin.</span></span> <span data-ttu-id="5427f-110">Wenn Sie Visual Studio nicht installieren, können Sie die SQLMetal-Datei auch über einen Download des [Windows SDK](https://go.microsoft.com/fwlink/?LinkId=142225)erhalten.</span><span class="sxs-lookup"><span data-stu-id="5427f-110">If you do not install Visual Studio, you can also get the SQLMetal file by downloading the [Windows SDK](https://go.microsoft.com/fwlink/?LinkId=142225).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5427f-111">Entwickler, die Visual Studio verwenden, können auch den objektrelationalen Designer verwenden, um Entitätsklassen zu generieren.</span><span class="sxs-lookup"><span data-stu-id="5427f-111">Developers who use Visual Studio can also use the Object Relational Designer to generate entity classes.</span></span> <span data-ttu-id="5427f-112">Die Befehlszeilenmethode ist für umfangreiche Datenbanken gut skalierbar.</span><span class="sxs-lookup"><span data-stu-id="5427f-112">The command-line approach scales well for large databases.</span></span> <span data-ttu-id="5427f-113">Da SqlMetal ein Befehlszeilentool ist, können Sie es in einem Buildprozess verwenden.</span><span class="sxs-lookup"><span data-stu-id="5427f-113">Because SqlMetal is a command-line tool, you can use it in a build process.</span></span>  
  
 <span data-ttu-id="5427f-114">Verwenden Sie die Developer-Eingabeaufforderung für Visual Studio (oder die Visual Studio-Eingabeaufforderung in Windows 7), um das Tool auszuführen.</span><span class="sxs-lookup"><span data-stu-id="5427f-114">To run the tool, use the Developer Command Prompt for Visual Studio (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="5427f-115">Weitere Informationen finden Sie unter [Command Prompts (Eingabeaufforderung)](developer-command-prompt-for-vs.md). Geben Sie bei er Eingabeaufforderung Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="5427f-115">For more information, see [Command Prompts](developer-command-prompt-for-vs.md).At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5427f-116">Syntax</span><span class="sxs-lookup"><span data-stu-id="5427f-116">Syntax</span></span>  
  
```console  
sqlmetal [options] [<input file>]  
```  
  
## <a name="options"></a><span data-ttu-id="5427f-117">Optionen</span><span class="sxs-lookup"><span data-stu-id="5427f-117">Options</span></span>  
 <span data-ttu-id="5427f-118">Geben Sie zum Anzeigen der aktuellsten Optionsliste `sqlmetal /?` in einer Eingabeaufforderung am installierten Speicherort ein.</span><span class="sxs-lookup"><span data-stu-id="5427f-118">To view the most current option list, type `sqlmetal /?` at a command prompt from the installed location.</span></span>  
  
 <span data-ttu-id="5427f-119">**Verbindungsoptionen**</span><span class="sxs-lookup"><span data-stu-id="5427f-119">**Connection Options**</span></span>  
  
|<span data-ttu-id="5427f-120">Option</span><span class="sxs-lookup"><span data-stu-id="5427f-120">Option</span></span>|<span data-ttu-id="5427f-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5427f-121">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="5427f-122">**/server:** *\<name>*</span><span class="sxs-lookup"><span data-stu-id="5427f-122">**/server:** *\<name>*</span></span>|<span data-ttu-id="5427f-123">Gibt den Datenbank-Servernamen an.</span><span class="sxs-lookup"><span data-stu-id="5427f-123">Specifies database server name.</span></span>|  
|<span data-ttu-id="5427f-124">**/database:** *\<name>*</span><span class="sxs-lookup"><span data-stu-id="5427f-124">**/database:** *\<name>*</span></span>|<span data-ttu-id="5427f-125">Gibt den Datenbankkatalog auf dem Server an.</span><span class="sxs-lookup"><span data-stu-id="5427f-125">Specifies database catalog on server.</span></span>|  
|<span data-ttu-id="5427f-126">**/user:** *\<name>*</span><span class="sxs-lookup"><span data-stu-id="5427f-126">**/user:** *\<name>*</span></span>|<span data-ttu-id="5427f-127">Gibt die Benutzer-ID für die Anmeldung an. Standardwert: Verwenden der Windows-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="5427f-127">Specifies logon user id. Default value: Use Windows authentication.</span></span>|  
|<span data-ttu-id="5427f-128">**/password:** *\<password>*</span><span class="sxs-lookup"><span data-stu-id="5427f-128">**/password:** *\<password>*</span></span>|<span data-ttu-id="5427f-129">Gibt das Anmeldekennwort an.</span><span class="sxs-lookup"><span data-stu-id="5427f-129">Specifies logon password.</span></span> <span data-ttu-id="5427f-130">Standardwert: Verwenden der Windows-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="5427f-130">Default value: Use Windows authentication.</span></span>|  
|<span data-ttu-id="5427f-131">**/conn:** *\<connection string>*</span><span class="sxs-lookup"><span data-stu-id="5427f-131">**/conn:** *\<connection string>*</span></span>|<span data-ttu-id="5427f-132">Gibt die Verbindungszeichenfolge für Datenbanken an.</span><span class="sxs-lookup"><span data-stu-id="5427f-132">Specifies database connection string.</span></span> <span data-ttu-id="5427f-133">Kann nicht mit den Optionen **/server**, **/database**, **/user**oder **/password** verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5427f-133">Cannot be used with **/server**, **/database**, **/user**, or **/password** options.</span></span><br /><br /> <span data-ttu-id="5427f-134">Die Verbindungszeichenfolge darf den Dateinamen nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="5427f-134">Do not include the file name in the connection string.</span></span> <span data-ttu-id="5427f-135">Fügen Sie stattdessen den Dateinamen in der Befehlszeile als Eingabedatei hinzu.</span><span class="sxs-lookup"><span data-stu-id="5427f-135">Instead, add the file name to the command line as the input file.</span></span> <span data-ttu-id="5427f-136">In der folgenden Zeile ist beispielsweise „c:\northwnd.mdf“ als Eingabedatei angegeben: **sqlmetal /code:"c:\northwind.cs" /language:csharp "c:\northwnd.mdf"** .</span><span class="sxs-lookup"><span data-stu-id="5427f-136">For example, the following line specifies "c:\northwnd.mdf" as the input file: **sqlmetal /code:"c:\northwind.cs" /language:csharp "c:\northwnd.mdf"**.</span></span>|  
|<span data-ttu-id="5427f-137">**/timeout:** *\<seconds>*</span><span class="sxs-lookup"><span data-stu-id="5427f-137">**/timeout:** *\<seconds>*</span></span>|<span data-ttu-id="5427f-138">Gibt den Timeoutwert an, wenn SqlMetal auf die Datenbank zugreift.</span><span class="sxs-lookup"><span data-stu-id="5427f-138">Specifies time-out value when SqlMetal accesses the database.</span></span> <span data-ttu-id="5427f-139">Standardwert: 0 (d. h. kein Zeitlimit).</span><span class="sxs-lookup"><span data-stu-id="5427f-139">Default value: 0 (that is, no time limit).</span></span>|  
  
 <span data-ttu-id="5427f-140">**Extraktionsoptionen**</span><span class="sxs-lookup"><span data-stu-id="5427f-140">**Extraction options**</span></span>  
  
|<span data-ttu-id="5427f-141">Option</span><span class="sxs-lookup"><span data-stu-id="5427f-141">Option</span></span>|<span data-ttu-id="5427f-142">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5427f-142">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="5427f-143">**/views**</span><span class="sxs-lookup"><span data-stu-id="5427f-143">**/views**</span></span>|<span data-ttu-id="5427f-144">Extrahiert Datenbankansichten.</span><span class="sxs-lookup"><span data-stu-id="5427f-144">Extracts database views.</span></span>|  
|<span data-ttu-id="5427f-145">**/functions**</span><span class="sxs-lookup"><span data-stu-id="5427f-145">**/functions**</span></span>|<span data-ttu-id="5427f-146">Extrahiert Datenbankfunktionen.</span><span class="sxs-lookup"><span data-stu-id="5427f-146">Extracts database functions.</span></span>|  
|<span data-ttu-id="5427f-147">**/sprocs**</span><span class="sxs-lookup"><span data-stu-id="5427f-147">**/sprocs**</span></span>|<span data-ttu-id="5427f-148">Extrahiert gespeicherte Prozeduren.</span><span class="sxs-lookup"><span data-stu-id="5427f-148">Extracts stored procedures.</span></span>|  
  
 <span data-ttu-id="5427f-149">**Ausgabeoptionen**</span><span class="sxs-lookup"><span data-stu-id="5427f-149">**Output options**</span></span>  
  
|<span data-ttu-id="5427f-150">Option</span><span class="sxs-lookup"><span data-stu-id="5427f-150">Option</span></span>|<span data-ttu-id="5427f-151">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5427f-151">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="5427f-152">**/dbml** *[:file]*</span><span class="sxs-lookup"><span data-stu-id="5427f-152">**/dbml** *[:file]*</span></span>|<span data-ttu-id="5427f-153">Sendet die Ausgabe als DBML-Datei.</span><span class="sxs-lookup"><span data-stu-id="5427f-153">Sends output as .dbml.</span></span> <span data-ttu-id="5427f-154">Kann nicht zusammen mit der Option **/map** verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5427f-154">Cannot be used with **/map** option.</span></span>|  
|<span data-ttu-id="5427f-155">**/code** *[:file]*</span><span class="sxs-lookup"><span data-stu-id="5427f-155">**/code** *[:file]*</span></span>|<span data-ttu-id="5427f-156">Sendet die Ausgabe als Quellcode.</span><span class="sxs-lookup"><span data-stu-id="5427f-156">Sends output as source code.</span></span> <span data-ttu-id="5427f-157">Kann nicht zusammen mit der Option **/dbml** verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5427f-157">Cannot be used with **/dbml** option.</span></span>|  
|<span data-ttu-id="5427f-158">**/map** *[:file]*</span><span class="sxs-lookup"><span data-stu-id="5427f-158">**/map** *[:file]*</span></span>|<span data-ttu-id="5427f-159">Generiert anstelle von Attributen eine XML-Zuordnungsdatei.</span><span class="sxs-lookup"><span data-stu-id="5427f-159">Generates an XML mapping file instead of attributes.</span></span> <span data-ttu-id="5427f-160">Kann nicht zusammen mit der Option **/dbml** verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5427f-160">Cannot be used with **/dbml** option.</span></span>|  
  
 <span data-ttu-id="5427f-161">**Verschiedenes**</span><span class="sxs-lookup"><span data-stu-id="5427f-161">**Miscellaneous**</span></span>  
  
|<span data-ttu-id="5427f-162">Option</span><span class="sxs-lookup"><span data-stu-id="5427f-162">Option</span></span>|<span data-ttu-id="5427f-163">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5427f-163">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="5427f-164">**/language:** *\<language>*</span><span class="sxs-lookup"><span data-stu-id="5427f-164">**/language:** *\<language>*</span></span>|<span data-ttu-id="5427f-165">Gibt die Quellcodesprache an.</span><span class="sxs-lookup"><span data-stu-id="5427f-165">Specifies source code language.</span></span><br /><br /> <span data-ttu-id="5427f-166">Gültige *\<<sprache>* : vb, csharp.</span><span class="sxs-lookup"><span data-stu-id="5427f-166">Valid *\<language>*: vb, csharp.</span></span><br /><br /> <span data-ttu-id="5427f-167">Standardwert: von der Erweiterung des Namens der Codedatei abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="5427f-167">Default value: Derived from extension on code file name.</span></span>|  
|<span data-ttu-id="5427f-168">**/namespace:** *\<name>*</span><span class="sxs-lookup"><span data-stu-id="5427f-168">**/namespace:** *\<name>*</span></span>|<span data-ttu-id="5427f-169">Gibt den Namespace des generierten Codes an.</span><span class="sxs-lookup"><span data-stu-id="5427f-169">Specifies namespace of the generated code.</span></span> <span data-ttu-id="5427f-170">Standardwert: kein Namespace.</span><span class="sxs-lookup"><span data-stu-id="5427f-170">Default value: no namespace.</span></span>|  
|<span data-ttu-id="5427f-171">**/context:** *\<type>*</span><span class="sxs-lookup"><span data-stu-id="5427f-171">**/context:** *\<type>*</span></span>|<span data-ttu-id="5427f-172">Gibt Namen der Datenkontextklasse an.</span><span class="sxs-lookup"><span data-stu-id="5427f-172">Specifies name of data context class.</span></span> <span data-ttu-id="5427f-173">Standardwert: vom Datenbanknamen abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="5427f-173">Default value: Derived from database name.</span></span>|  
|<span data-ttu-id="5427f-174">**/entitybase:** *\<type>*</span><span class="sxs-lookup"><span data-stu-id="5427f-174">**/entitybase:** *\<type>*</span></span>|<span data-ttu-id="5427f-175">Gibt die Basisklasse der Entitätsklassen im generierten Code an.</span><span class="sxs-lookup"><span data-stu-id="5427f-175">Specifies the base class of the entity classes in the generated code.</span></span> <span data-ttu-id="5427f-176">Standardwert: Entitäten verfügen über keine Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="5427f-176">Default value: Entities have no base class.</span></span>|  
|<span data-ttu-id="5427f-177">**/pluralize**</span><span class="sxs-lookup"><span data-stu-id="5427f-177">**/pluralize**</span></span>|<span data-ttu-id="5427f-178">Klassen- und Membernamen werden automatisch in Plural- oder Singularform verwendet.</span><span class="sxs-lookup"><span data-stu-id="5427f-178">Automatically pluralizes or singularizes class and member names.</span></span><br /><br /> <span data-ttu-id="5427f-179">Diese Option ist nur in der englischen Version (US-Version) verfügbar.</span><span class="sxs-lookup"><span data-stu-id="5427f-179">This option is available only in the U.S. English version.</span></span>|  
|<span data-ttu-id="5427f-180">**/serialization:** *\<option>*</span><span class="sxs-lookup"><span data-stu-id="5427f-180">**/serialization:** *\<option>*</span></span>|<span data-ttu-id="5427f-181">Generiert serialisierbare Klassen.</span><span class="sxs-lookup"><span data-stu-id="5427f-181">Generates serializable classes.</span></span><br /><br /> <span data-ttu-id="5427f-182">Gültige *\<option>* : None, Unidirectional.</span><span class="sxs-lookup"><span data-stu-id="5427f-182">Valid *\<option>*: None, Unidirectional.</span></span> <span data-ttu-id="5427f-183">Standardwert: Keine</span><span class="sxs-lookup"><span data-stu-id="5427f-183">Default value: None.</span></span><br /><br /> <span data-ttu-id="5427f-184">Weitere Informationen finden Sie unter [Serialization (Serialisierung)](../data/adonet/sql/linq/serialization.md).</span><span class="sxs-lookup"><span data-stu-id="5427f-184">For more information, see [Serialization](../data/adonet/sql/linq/serialization.md).</span></span>|  
  
 <span data-ttu-id="5427f-185">**Eingabedatei**</span><span class="sxs-lookup"><span data-stu-id="5427f-185">**Input File**</span></span>  
  
|<span data-ttu-id="5427f-186">Option</span><span class="sxs-lookup"><span data-stu-id="5427f-186">Option</span></span>|<span data-ttu-id="5427f-187">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5427f-187">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="5427f-188">**\<eingabedatei>**</span><span class="sxs-lookup"><span data-stu-id="5427f-188">**\<input file>**</span></span>|<span data-ttu-id="5427f-189">Gibt eine SQL Server Express-Datei (.mdf), eine SQL Server Compact 3.5-Datei (.sdf) oder eine Zwischendatei (.dbml) an.</span><span class="sxs-lookup"><span data-stu-id="5427f-189">Specifies a SQL Server Express .mdf file, a SQL Server Compact 3.5 .sdf file, or a .dbml intermediate file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5427f-190">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5427f-190">Remarks</span></span>  
 <span data-ttu-id="5427f-191">Die SqlMetal-Funktionalität umfasst eigentlich zwei Schritte:</span><span class="sxs-lookup"><span data-stu-id="5427f-191">SqlMetal functionality actually involves two steps:</span></span>  
  
- <span data-ttu-id="5427f-192">Extrahieren der Datenbank-Metadaten in eine DBML-Datei</span><span class="sxs-lookup"><span data-stu-id="5427f-192">Extracting the metadata of the database into a .dbml file.</span></span>  
  
- <span data-ttu-id="5427f-193">Generieren einer Codeausgabedatei</span><span class="sxs-lookup"><span data-stu-id="5427f-193">Generating a code output file.</span></span>  
  
     <span data-ttu-id="5427f-194">Durch Verwenden der entsprechenden Befehlszeilenoptionen können Sie Visual Basic- oder C#-Quellcode bzw. eine XML-Zuordnungsdatei erstellen.</span><span class="sxs-lookup"><span data-stu-id="5427f-194">By using the appropriate command-line options, you can produce Visual Basic or C# source code, or you can produce an XML mapping file.</span></span>  
  
 <span data-ttu-id="5427f-195">Um die Metadaten aus einer MDF-Datei zu extrahieren, müssen Sie den Namen der MDF-Datei nach allen anderen Optionen eingeben.</span><span class="sxs-lookup"><span data-stu-id="5427f-195">To extract the metadata from an .mdf file, you must specify the name of the .mdf file after all other options.</span></span>  
  
 <span data-ttu-id="5427f-196">Wenn **/Server** nicht angegeben ist, wird **localhost/sqlexpress** angenommen.</span><span class="sxs-lookup"><span data-stu-id="5427f-196">If no **/server** is specified, **localhost/sqlexpress** is assumed.</span></span>  
  
 <span data-ttu-id="5427f-197">Microsoft SQL Server 2005 löst eine Ausnahme aus, wenn mindestens eine der folgenden Bedingungen erfüllt ist:</span><span class="sxs-lookup"><span data-stu-id="5427f-197">Microsoft SQL Server 2005 throws an exception if one or more of the following conditions are true:</span></span>  
  
- <span data-ttu-id="5427f-198">SqlMetal versucht, eine gespeicherte Prozedur zu extrahieren, die sich selbst aufruft.</span><span class="sxs-lookup"><span data-stu-id="5427f-198">SqlMetal tries to extract a stored procedure that calls itself.</span></span>  
  
- <span data-ttu-id="5427f-199">Die Schachtelungsebene einer gespeicherten Prozedur, Funktion, oder Ansicht übersteigt 32.</span><span class="sxs-lookup"><span data-stu-id="5427f-199">The nesting level of a stored procedure, function, or view exceeds 32.</span></span>  
  
     <span data-ttu-id="5427f-200">SqlMetal fängt diese Ausnahme ab und gibt sie als Warnung aus.</span><span class="sxs-lookup"><span data-stu-id="5427f-200">SqlMetal catches this exception and reports it as a warning.</span></span>  
  
 <span data-ttu-id="5427f-201">Um einen Namen für eine Eingabedatei anzugeben, fügen Sie den Namen der Befehlszeile als Eingabedatei hinzu.</span><span class="sxs-lookup"><span data-stu-id="5427f-201">To specify an input file name, add the name to the command line as the input file.</span></span> <span data-ttu-id="5427f-202">Die Angabe des Dateinamens in der Verbindungszeichenfolge (mithilfe der Option **/conn** ) wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5427f-202">Including the file name in the connection string (using the **/conn** option) is not supported.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="5427f-203">Beispiele</span><span class="sxs-lookup"><span data-stu-id="5427f-203">Examples</span></span>  
 <span data-ttu-id="5427f-204">Generiert eine DBML-Datei, die extrahierte SQL-Metadaten umfasst:</span><span class="sxs-lookup"><span data-stu-id="5427f-204">Generate a .dbml file that includes extracted SQL metadata:</span></span>  
  
 <span data-ttu-id="5427f-205">**sqlmetal /server:myserver /database:northwind /dbml:mymeta.dbml**</span><span class="sxs-lookup"><span data-stu-id="5427f-205">**sqlmetal /server:myserver /database:northwind /dbml:mymeta.dbml**</span></span>  
  
 <span data-ttu-id="5427f-206">Generiert mithilfe von SQL Server Express eine DBML-Datei, die extrahierte SQL-Metadaten aus einer MDF-Datei umfasst:</span><span class="sxs-lookup"><span data-stu-id="5427f-206">Generate a .dbml file that includes extracted SQL metadata from an .mdf file by using SQL Server Express:</span></span>  
  
 <span data-ttu-id="5427f-207">**sqlmetal /dbml:mymeta.dbml mydbfile.mdf**</span><span class="sxs-lookup"><span data-stu-id="5427f-207">**sqlmetal /dbml:mymeta.dbml mydbfile.mdf**</span></span>  
  
 <span data-ttu-id="5427f-208">Generiert aus SQL Server Express eine DBML-Datei, die extrahierte SQL-Metadaten umfasst:</span><span class="sxs-lookup"><span data-stu-id="5427f-208">Generate a .dbml file that includes extracted SQL metadata from SQL Server Express:</span></span>  
  
 <span data-ttu-id="5427f-209">**sqlmetal /server:.\sqlexpress /dbml:mymeta.dbml /database:northwind**</span><span class="sxs-lookup"><span data-stu-id="5427f-209">**sqlmetal /server:.\sqlexpress /dbml:mymeta.dbml /database:northwind**</span></span>  
  
 <span data-ttu-id="5427f-210">Generiert Quellcode aus einer DBML-Metadatendatei:</span><span class="sxs-lookup"><span data-stu-id="5427f-210">Generate source code from a .dbml metadata file:</span></span>  
  
 <span data-ttu-id="5427f-211">**sqlmetal /namespace:nwind /code:nwind.cs /language:csharp mymetal.dbml**</span><span class="sxs-lookup"><span data-stu-id="5427f-211">**sqlmetal /namespace:nwind /code:nwind.cs /language:csharp mymetal.dbml**</span></span>  
  
 <span data-ttu-id="5427f-212">Generiert Quellcode direkt aus SQL-Metadaten:</span><span class="sxs-lookup"><span data-stu-id="5427f-212">Generate source code from SQL metadata directly:</span></span>  
  
 <span data-ttu-id="5427f-213">**sqlmetal /server:myserver /database:northwind /namespace:nwind /code:nwind.cs /language:csharp**</span><span class="sxs-lookup"><span data-stu-id="5427f-213">**sqlmetal /server:myserver /database:northwind /namespace:nwind /code:nwind.cs /language:csharp**</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5427f-214">Wenn Sie die Option **/pluralize** mit der Northwind-Beispieldatenbank verwenden, stellen Sie folgendes Verhalten fest.</span><span class="sxs-lookup"><span data-stu-id="5427f-214">When you use the **/pluralize** option with the Northwind sample database, note the following behavior.</span></span> <span data-ttu-id="5427f-215">Wenn SqlMetal Zeilentypnamen für Tabellen erstellt, wird für Tabellennamen die Singularform verwendet.</span><span class="sxs-lookup"><span data-stu-id="5427f-215">When SqlMetal makes row-type names for tables, the table names are singular.</span></span> <span data-ttu-id="5427f-216">Wenn <xref:System.Data.Linq.DataContext> -Eigenschaften für Tabellen erstellt werden, wird für Tabellennamen die Pluralform verwendet.</span><span class="sxs-lookup"><span data-stu-id="5427f-216">When it makes <xref:System.Data.Linq.DataContext> properties for tables, the table names are plural.</span></span> <span data-ttu-id="5427f-217">Zufällig treten die Tabellen in der Northwind-Beispieldatenbank bereits in Pluralform auf.</span><span class="sxs-lookup"><span data-stu-id="5427f-217">Coincidentally, the tables in the Northwind sample database are already plural.</span></span> <span data-ttu-id="5427f-218">Deshalb ist nicht erkennbar, dass dieser Schritt funktioniert.</span><span class="sxs-lookup"><span data-stu-id="5427f-218">Therefore, you do not see that part working.</span></span> <span data-ttu-id="5427f-219">Obwohl es üblich ist, Datenbanktabellen im Singular zu benennen, ist es in .NET auch verbreitet, Auflistungen in Pluralform zu benennen.</span><span class="sxs-lookup"><span data-stu-id="5427f-219">Although it is common practice to name database tables singular, it is also a common practice in .NET to name collections plural.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5427f-220">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5427f-220">See also</span></span>

- [<span data-ttu-id="5427f-221">How to: (Vorgehensweise: Generieren des Objektmodells in Visual Basic oder C#)</span><span class="sxs-lookup"><span data-stu-id="5427f-221">How to: Generate the Object Model in Visual Basic or C#</span></span>](../data/adonet/sql/linq/how-to-generate-the-object-model-in-visual-basic-or-csharp.md)
- [<span data-ttu-id="5427f-222">Codegenerierung in LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="5427f-222">Code Generation in LINQ to SQL</span></span>](../data/adonet/sql/linq/code-generation-in-linq-to-sql.md)
- [<span data-ttu-id="5427f-223">External Mapping (Externe Zuordnung)</span><span class="sxs-lookup"><span data-stu-id="5427f-223">External Mapping</span></span>](../data/adonet/sql/linq/external-mapping.md)

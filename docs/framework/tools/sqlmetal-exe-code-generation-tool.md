---
title: SqlMetal.exe (Tool zur Codegenerierung)
description: Informieren Sie sich über „SqlMetal.exe“, das Tool zur Codegenerierung. Verwenden Sie das Tool, um Code und Zuordnungen für die LINQ to SQL-Komponente von .NET zu generieren.
ms.date: 03/30/2017
helpviewer_keywords:
- SQLMetal [LINQ to SQL]
- code generation tool
- SQLMetal.exe
- LINQ to SQL, serialization
- LINQ to SQL, DBML files
- LINQ to SQL, SQLMetal
ms.assetid: 819e5a96-7646-4fdb-b14b-fe31221b0614
ms.openlocfilehash: 4edf11315892ed8267bee17d69a70033348eca5c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96272565"
---
# <a name="sqlmetalexe-code-generation-tool"></a><span data-ttu-id="5e39d-104">SqlMetal.exe (Tool zur Codegenerierung)</span><span class="sxs-lookup"><span data-stu-id="5e39d-104">SqlMetal.exe (Code Generation Tool)</span></span>

<span data-ttu-id="5e39d-105">Das SqlMetal-Befehlszeilentool generiert Code und Zuordnungen für die [!INCLUDE[vbtecdlinq](../../../includes/vbtecdlinq-md.md)]-Komponente von .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5e39d-105">The SqlMetal command-line tool generates code and mapping for the [!INCLUDE[vbtecdlinq](../../../includes/vbtecdlinq-md.md)] component of the .NET Framework.</span></span> <span data-ttu-id="5e39d-106">Durch Anwenden der später in diesem Thema behandelten Optionen können Sie SqlMetal anweisen, mehrere verschiedene Aktionen wie etwa die folgenden auszuführen:</span><span class="sxs-lookup"><span data-stu-id="5e39d-106">By applying options that appear later in this topic, you can instruct SqlMetal to perform several different actions that include the following:</span></span>  
  
- <span data-ttu-id="5e39d-107">Generieren von Quellcode und Zuordnungsattributen oder einer Zuordnungsdatei von einer Datenbank aus</span><span class="sxs-lookup"><span data-stu-id="5e39d-107">From a database, generate source code and mapping attributes or a mapping file.</span></span>  
  
- <span data-ttu-id="5e39d-108">Generieren einer DBML-Datei (Intermediate Database Markup Language) zum Anpassen von einer Datenbank aus</span><span class="sxs-lookup"><span data-stu-id="5e39d-108">From a database, generate an intermediate database markup language (.dbml) file for customization.</span></span>  
  
- <span data-ttu-id="5e39d-109">Generieren von Code und Zuordnungsattributen oder einer Zuordnungsdatei von einer DBML-Datei aus</span><span class="sxs-lookup"><span data-stu-id="5e39d-109">From a .dbml file, generate code and mapping attributes or a mapping file.</span></span>  
  
 <span data-ttu-id="5e39d-110">Dieses Tool wird automatisch mit Visual Studio installiert.</span><span class="sxs-lookup"><span data-stu-id="5e39d-110">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="5e39d-111">Standardmäßig befindet sich die Datei unter " `drive`:\Programme\Microsoft SDKs\Windows\v`n.nn`\bin".</span><span class="sxs-lookup"><span data-stu-id="5e39d-111">By default, the file is located at `drive`:\Program Files\Microsoft SDKs\Windows\v`n.nn`\bin.</span></span> <span data-ttu-id="5e39d-112">Wenn Sie Visual Studio nicht installieren, können Sie die SQLMetal-Datei auch über einen Download des [Windows SDK](https://go.microsoft.com/fwlink/?LinkId=142225)erhalten.</span><span class="sxs-lookup"><span data-stu-id="5e39d-112">If you do not install Visual Studio, you can also get the SQLMetal file by downloading the [Windows SDK](https://go.microsoft.com/fwlink/?LinkId=142225).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5e39d-113">Entwickler, die Visual Studio verwenden, können auch den objektrelationalen Designer verwenden, um Entitätsklassen zu generieren.</span><span class="sxs-lookup"><span data-stu-id="5e39d-113">Developers who use Visual Studio can also use the Object Relational Designer to generate entity classes.</span></span> <span data-ttu-id="5e39d-114">Die Befehlszeilenmethode ist für umfangreiche Datenbanken gut skalierbar.</span><span class="sxs-lookup"><span data-stu-id="5e39d-114">The command-line approach scales well for large databases.</span></span> <span data-ttu-id="5e39d-115">Da SqlMetal ein Befehlszeilentool ist, können Sie es in einem Buildprozess verwenden.</span><span class="sxs-lookup"><span data-stu-id="5e39d-115">Because SqlMetal is a command-line tool, you can use it in a build process.</span></span>  
  
 <span data-ttu-id="5e39d-116">Verwenden Sie die Developer-Eingabeaufforderung für Visual Studio (oder die Visual Studio-Eingabeaufforderung in Windows 7), um das Tool auszuführen.</span><span class="sxs-lookup"><span data-stu-id="5e39d-116">To run the tool, use the Developer Command Prompt for Visual Studio (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="5e39d-117">Weitere Informationen finden Sie unter [Command Prompts (Eingabeaufforderung)](developer-command-prompt-for-vs.md). Geben Sie bei er Eingabeaufforderung Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="5e39d-117">For more information, see [Command Prompts](developer-command-prompt-for-vs.md).At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e39d-118">Syntax</span><span class="sxs-lookup"><span data-stu-id="5e39d-118">Syntax</span></span>  
  
```console  
sqlmetal [options] [<input file>]  
```  
  
## <a name="options"></a><span data-ttu-id="5e39d-119">Tastatur</span><span class="sxs-lookup"><span data-stu-id="5e39d-119">Options</span></span>  

 <span data-ttu-id="5e39d-120">Geben Sie zum Anzeigen der aktuellsten Optionsliste `sqlmetal /?` in einer Eingabeaufforderung am installierten Speicherort ein.</span><span class="sxs-lookup"><span data-stu-id="5e39d-120">To view the most current option list, type `sqlmetal /?` at a command prompt from the installed location.</span></span>  
  
 <span data-ttu-id="5e39d-121">**Verbindungsoptionen**</span><span class="sxs-lookup"><span data-stu-id="5e39d-121">**Connection Options**</span></span>  
  
|<span data-ttu-id="5e39d-122">Option</span><span class="sxs-lookup"><span data-stu-id="5e39d-122">Option</span></span>|<span data-ttu-id="5e39d-123">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5e39d-123">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="5e39d-124">**/server:** *\<name>*</span><span class="sxs-lookup"><span data-stu-id="5e39d-124">**/server:** *\<name>*</span></span>|<span data-ttu-id="5e39d-125">Gibt den Datenbank-Servernamen an.</span><span class="sxs-lookup"><span data-stu-id="5e39d-125">Specifies database server name.</span></span>|  
|<span data-ttu-id="5e39d-126">**/database:** *\<name>*</span><span class="sxs-lookup"><span data-stu-id="5e39d-126">**/database:** *\<name>*</span></span>|<span data-ttu-id="5e39d-127">Gibt den Datenbankkatalog auf dem Server an.</span><span class="sxs-lookup"><span data-stu-id="5e39d-127">Specifies database catalog on server.</span></span>|  
|<span data-ttu-id="5e39d-128">**/user:** *\<name>*</span><span class="sxs-lookup"><span data-stu-id="5e39d-128">**/user:** *\<name>*</span></span>|<span data-ttu-id="5e39d-129">Gibt die Benutzer-ID für die Anmeldung an. Standardwert: Verwenden der Windows-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="5e39d-129">Specifies logon user id. Default value: Use Windows authentication.</span></span>|  
|<span data-ttu-id="5e39d-130">**/password:** *\<password>*</span><span class="sxs-lookup"><span data-stu-id="5e39d-130">**/password:** *\<password>*</span></span>|<span data-ttu-id="5e39d-131">Gibt das Anmeldekennwort an.</span><span class="sxs-lookup"><span data-stu-id="5e39d-131">Specifies logon password.</span></span> <span data-ttu-id="5e39d-132">Standardwert: Verwenden der Windows-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="5e39d-132">Default value: Use Windows authentication.</span></span>|  
|<span data-ttu-id="5e39d-133">**/conn:** *\<connection string>*</span><span class="sxs-lookup"><span data-stu-id="5e39d-133">**/conn:** *\<connection string>*</span></span>|<span data-ttu-id="5e39d-134">Gibt die Verbindungszeichenfolge für Datenbanken an.</span><span class="sxs-lookup"><span data-stu-id="5e39d-134">Specifies database connection string.</span></span> <span data-ttu-id="5e39d-135">Kann nicht mit den Optionen **/server**, **/database**, **/user** oder **/password** verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5e39d-135">Cannot be used with **/server**, **/database**, **/user**, or **/password** options.</span></span><br /><br /> <span data-ttu-id="5e39d-136">Die Verbindungszeichenfolge darf den Dateinamen nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="5e39d-136">Do not include the file name in the connection string.</span></span> <span data-ttu-id="5e39d-137">Fügen Sie stattdessen den Dateinamen in der Befehlszeile als Eingabedatei hinzu.</span><span class="sxs-lookup"><span data-stu-id="5e39d-137">Instead, add the file name to the command line as the input file.</span></span> <span data-ttu-id="5e39d-138">In der folgenden Zeile ist beispielsweise „c:\northwnd.mdf“ als Eingabedatei angegeben: **sqlmetal /code:"c:\northwind.cs" /language:csharp "c:\northwnd.mdf"** .</span><span class="sxs-lookup"><span data-stu-id="5e39d-138">For example, the following line specifies "c:\northwnd.mdf" as the input file: **sqlmetal /code:"c:\northwind.cs" /language:csharp "c:\northwnd.mdf"**.</span></span>|  
|<span data-ttu-id="5e39d-139">**/timeout:** *\<seconds>*</span><span class="sxs-lookup"><span data-stu-id="5e39d-139">**/timeout:** *\<seconds>*</span></span>|<span data-ttu-id="5e39d-140">Gibt den Timeoutwert an, wenn SqlMetal auf die Datenbank zugreift.</span><span class="sxs-lookup"><span data-stu-id="5e39d-140">Specifies time-out value when SqlMetal accesses the database.</span></span> <span data-ttu-id="5e39d-141">Standardwert: 0 (d. h. kein Zeitlimit).</span><span class="sxs-lookup"><span data-stu-id="5e39d-141">Default value: 0 (that is, no time limit).</span></span>|  
  
 <span data-ttu-id="5e39d-142">**Extraktionsoptionen**</span><span class="sxs-lookup"><span data-stu-id="5e39d-142">**Extraction options**</span></span>  
  
|<span data-ttu-id="5e39d-143">Option</span><span class="sxs-lookup"><span data-stu-id="5e39d-143">Option</span></span>|<span data-ttu-id="5e39d-144">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5e39d-144">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="5e39d-145">**/views**</span><span class="sxs-lookup"><span data-stu-id="5e39d-145">**/views**</span></span>|<span data-ttu-id="5e39d-146">Extrahiert Datenbankansichten.</span><span class="sxs-lookup"><span data-stu-id="5e39d-146">Extracts database views.</span></span>|  
|<span data-ttu-id="5e39d-147">**/functions**</span><span class="sxs-lookup"><span data-stu-id="5e39d-147">**/functions**</span></span>|<span data-ttu-id="5e39d-148">Extrahiert Datenbankfunktionen.</span><span class="sxs-lookup"><span data-stu-id="5e39d-148">Extracts database functions.</span></span>|  
|<span data-ttu-id="5e39d-149">**/sprocs**</span><span class="sxs-lookup"><span data-stu-id="5e39d-149">**/sprocs**</span></span>|<span data-ttu-id="5e39d-150">Extrahiert gespeicherte Prozeduren.</span><span class="sxs-lookup"><span data-stu-id="5e39d-150">Extracts stored procedures.</span></span>|  
  
 <span data-ttu-id="5e39d-151">**Ausgabeoptionen**</span><span class="sxs-lookup"><span data-stu-id="5e39d-151">**Output options**</span></span>  
  
|<span data-ttu-id="5e39d-152">Option</span><span class="sxs-lookup"><span data-stu-id="5e39d-152">Option</span></span>|<span data-ttu-id="5e39d-153">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5e39d-153">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="5e39d-154">**/dbml** *[:file]*</span><span class="sxs-lookup"><span data-stu-id="5e39d-154">**/dbml** *[:file]*</span></span>|<span data-ttu-id="5e39d-155">Sendet die Ausgabe als DBML-Datei.</span><span class="sxs-lookup"><span data-stu-id="5e39d-155">Sends output as .dbml.</span></span> <span data-ttu-id="5e39d-156">Kann nicht zusammen mit der Option **/map** verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5e39d-156">Cannot be used with **/map** option.</span></span>|  
|<span data-ttu-id="5e39d-157">**/code** *[:file]*</span><span class="sxs-lookup"><span data-stu-id="5e39d-157">**/code** *[:file]*</span></span>|<span data-ttu-id="5e39d-158">Sendet die Ausgabe als Quellcode.</span><span class="sxs-lookup"><span data-stu-id="5e39d-158">Sends output as source code.</span></span> <span data-ttu-id="5e39d-159">Kann nicht zusammen mit der Option **/dbml** verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5e39d-159">Cannot be used with **/dbml** option.</span></span>|  
|<span data-ttu-id="5e39d-160">**/map** *[:file]*</span><span class="sxs-lookup"><span data-stu-id="5e39d-160">**/map** *[:file]*</span></span>|<span data-ttu-id="5e39d-161">Generiert anstelle von Attributen eine XML-Zuordnungsdatei.</span><span class="sxs-lookup"><span data-stu-id="5e39d-161">Generates an XML mapping file instead of attributes.</span></span> <span data-ttu-id="5e39d-162">Kann nicht zusammen mit der Option **/dbml** verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5e39d-162">Cannot be used with **/dbml** option.</span></span>|  
  
 <span data-ttu-id="5e39d-163">**Verschiedenes**</span><span class="sxs-lookup"><span data-stu-id="5e39d-163">**Miscellaneous**</span></span>  
  
|<span data-ttu-id="5e39d-164">Option</span><span class="sxs-lookup"><span data-stu-id="5e39d-164">Option</span></span>|<span data-ttu-id="5e39d-165">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5e39d-165">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="5e39d-166">**/language:** *\<language>*</span><span class="sxs-lookup"><span data-stu-id="5e39d-166">**/language:** *\<language>*</span></span>|<span data-ttu-id="5e39d-167">Gibt die Quellcodesprache an.</span><span class="sxs-lookup"><span data-stu-id="5e39d-167">Specifies source code language.</span></span><br /><br /> <span data-ttu-id="5e39d-168">Gültige *\<language>* : vb, csharp.</span><span class="sxs-lookup"><span data-stu-id="5e39d-168">Valid *\<language>*: vb, csharp.</span></span><br /><br /> <span data-ttu-id="5e39d-169">Standardwert: von der Erweiterung des Namens der Codedatei abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="5e39d-169">Default value: Derived from extension on code file name.</span></span>|  
|<span data-ttu-id="5e39d-170">**/namespace:** *\<name>*</span><span class="sxs-lookup"><span data-stu-id="5e39d-170">**/namespace:** *\<name>*</span></span>|<span data-ttu-id="5e39d-171">Gibt den Namespace des generierten Codes an.</span><span class="sxs-lookup"><span data-stu-id="5e39d-171">Specifies namespace of the generated code.</span></span> <span data-ttu-id="5e39d-172">Standardwert: kein Namespace.</span><span class="sxs-lookup"><span data-stu-id="5e39d-172">Default value: no namespace.</span></span>|  
|<span data-ttu-id="5e39d-173">**/context:** *\<type>*</span><span class="sxs-lookup"><span data-stu-id="5e39d-173">**/context:** *\<type>*</span></span>|<span data-ttu-id="5e39d-174">Gibt Namen der Datenkontextklasse an.</span><span class="sxs-lookup"><span data-stu-id="5e39d-174">Specifies name of data context class.</span></span> <span data-ttu-id="5e39d-175">Standardwert: vom Datenbanknamen abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="5e39d-175">Default value: Derived from database name.</span></span>|  
|<span data-ttu-id="5e39d-176">**/entitybase:** *\<type>*</span><span class="sxs-lookup"><span data-stu-id="5e39d-176">**/entitybase:** *\<type>*</span></span>|<span data-ttu-id="5e39d-177">Gibt die Basisklasse der Entitätsklassen im generierten Code an.</span><span class="sxs-lookup"><span data-stu-id="5e39d-177">Specifies the base class of the entity classes in the generated code.</span></span> <span data-ttu-id="5e39d-178">Standardwert: Entitäten verfügen über keine Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="5e39d-178">Default value: Entities have no base class.</span></span>|  
|<span data-ttu-id="5e39d-179">**/pluralize**</span><span class="sxs-lookup"><span data-stu-id="5e39d-179">**/pluralize**</span></span>|<span data-ttu-id="5e39d-180">Klassen- und Membernamen werden automatisch in Plural- oder Singularform verwendet.</span><span class="sxs-lookup"><span data-stu-id="5e39d-180">Automatically pluralizes or singularizes class and member names.</span></span><br /><br /> <span data-ttu-id="5e39d-181">Diese Option ist nur in der englischen Version (US-Version) verfügbar.</span><span class="sxs-lookup"><span data-stu-id="5e39d-181">This option is available only in the U.S. English version.</span></span>|  
|<span data-ttu-id="5e39d-182">**/serialization:** *\<option>*</span><span class="sxs-lookup"><span data-stu-id="5e39d-182">**/serialization:** *\<option>*</span></span>|<span data-ttu-id="5e39d-183">Generiert serialisierbare Klassen.</span><span class="sxs-lookup"><span data-stu-id="5e39d-183">Generates serializable classes.</span></span><br /><br /> <span data-ttu-id="5e39d-184">Gültige *\<option>* : None, Unidirectional.</span><span class="sxs-lookup"><span data-stu-id="5e39d-184">Valid *\<option>*: None, Unidirectional.</span></span> <span data-ttu-id="5e39d-185">Standardwert: Keine</span><span class="sxs-lookup"><span data-stu-id="5e39d-185">Default value: None.</span></span><br /><br /> <span data-ttu-id="5e39d-186">Weitere Informationen finden Sie unter [Serialization (Serialisierung)](../data/adonet/sql/linq/serialization.md).</span><span class="sxs-lookup"><span data-stu-id="5e39d-186">For more information, see [Serialization](../data/adonet/sql/linq/serialization.md).</span></span>|  
  
 <span data-ttu-id="5e39d-187">**Eingabedatei**</span><span class="sxs-lookup"><span data-stu-id="5e39d-187">**Input File**</span></span>  
  
|<span data-ttu-id="5e39d-188">Option</span><span class="sxs-lookup"><span data-stu-id="5e39d-188">Option</span></span>|<span data-ttu-id="5e39d-189">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5e39d-189">Description</span></span>|  
|------------|-----------------|  
|**\<input file>**|<span data-ttu-id="5e39d-190">Gibt eine SQL Server Express-Datei (.mdf), eine SQL Server Compact 3.5-Datei (.sdf) oder eine Zwischendatei (.dbml) an.</span><span class="sxs-lookup"><span data-stu-id="5e39d-190">Specifies a SQL Server Express .mdf file, a SQL Server Compact 3.5 .sdf file, or a .dbml intermediate file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5e39d-191">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5e39d-191">Remarks</span></span>  

 <span data-ttu-id="5e39d-192">Die SqlMetal-Funktionalität umfasst eigentlich zwei Schritte:</span><span class="sxs-lookup"><span data-stu-id="5e39d-192">SqlMetal functionality actually involves two steps:</span></span>  
  
- <span data-ttu-id="5e39d-193">Extrahieren der Datenbank-Metadaten in eine DBML-Datei</span><span class="sxs-lookup"><span data-stu-id="5e39d-193">Extracting the metadata of the database into a .dbml file.</span></span>  
  
- <span data-ttu-id="5e39d-194">Generieren einer Codeausgabedatei</span><span class="sxs-lookup"><span data-stu-id="5e39d-194">Generating a code output file.</span></span>  
  
     <span data-ttu-id="5e39d-195">Durch Verwenden der entsprechenden Befehlszeilenoptionen können Sie Visual Basic- oder C#-Quellcode bzw. eine XML-Zuordnungsdatei erstellen.</span><span class="sxs-lookup"><span data-stu-id="5e39d-195">By using the appropriate command-line options, you can produce Visual Basic or C# source code, or you can produce an XML mapping file.</span></span>  
  
 <span data-ttu-id="5e39d-196">Um die Metadaten aus einer MDF-Datei zu extrahieren, müssen Sie den Namen der MDF-Datei nach allen anderen Optionen eingeben.</span><span class="sxs-lookup"><span data-stu-id="5e39d-196">To extract the metadata from an .mdf file, you must specify the name of the .mdf file after all other options.</span></span>  
  
 <span data-ttu-id="5e39d-197">Wenn **/Server** nicht angegeben ist, wird **localhost/sqlexpress** angenommen.</span><span class="sxs-lookup"><span data-stu-id="5e39d-197">If no **/server** is specified, **localhost/sqlexpress** is assumed.</span></span>  
  
 <span data-ttu-id="5e39d-198">Microsoft SQL Server 2005 löst eine Ausnahme aus, wenn mindestens eine der folgenden Bedingungen erfüllt ist:</span><span class="sxs-lookup"><span data-stu-id="5e39d-198">Microsoft SQL Server 2005 throws an exception if one or more of the following conditions are true:</span></span>  
  
- <span data-ttu-id="5e39d-199">SqlMetal versucht, eine gespeicherte Prozedur zu extrahieren, die sich selbst aufruft.</span><span class="sxs-lookup"><span data-stu-id="5e39d-199">SqlMetal tries to extract a stored procedure that calls itself.</span></span>  
  
- <span data-ttu-id="5e39d-200">Die Schachtelungsebene einer gespeicherten Prozedur, Funktion, oder Ansicht übersteigt 32.</span><span class="sxs-lookup"><span data-stu-id="5e39d-200">The nesting level of a stored procedure, function, or view exceeds 32.</span></span>  
  
     <span data-ttu-id="5e39d-201">SqlMetal fängt diese Ausnahme ab und gibt sie als Warnung aus.</span><span class="sxs-lookup"><span data-stu-id="5e39d-201">SqlMetal catches this exception and reports it as a warning.</span></span>  
  
 <span data-ttu-id="5e39d-202">Um einen Namen für eine Eingabedatei anzugeben, fügen Sie den Namen der Befehlszeile als Eingabedatei hinzu.</span><span class="sxs-lookup"><span data-stu-id="5e39d-202">To specify an input file name, add the name to the command line as the input file.</span></span> <span data-ttu-id="5e39d-203">Die Angabe des Dateinamens in der Verbindungszeichenfolge (mithilfe der Option **/conn** ) wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5e39d-203">Including the file name in the connection string (using the **/conn** option) is not supported.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="5e39d-204">Beispiele</span><span class="sxs-lookup"><span data-stu-id="5e39d-204">Examples</span></span>  

 <span data-ttu-id="5e39d-205">Generiert eine DBML-Datei, die extrahierte SQL-Metadaten umfasst:</span><span class="sxs-lookup"><span data-stu-id="5e39d-205">Generate a .dbml file that includes extracted SQL metadata:</span></span>  
  
 <span data-ttu-id="5e39d-206">**sqlmetal /server:myserver /database:northwind /dbml:mymeta.dbml**</span><span class="sxs-lookup"><span data-stu-id="5e39d-206">**sqlmetal /server:myserver /database:northwind /dbml:mymeta.dbml**</span></span>  
  
 <span data-ttu-id="5e39d-207">Generiert mithilfe von SQL Server Express eine DBML-Datei, die extrahierte SQL-Metadaten aus einer MDF-Datei umfasst:</span><span class="sxs-lookup"><span data-stu-id="5e39d-207">Generate a .dbml file that includes extracted SQL metadata from an .mdf file by using SQL Server Express:</span></span>  
  
 <span data-ttu-id="5e39d-208">**sqlmetal /dbml:mymeta.dbml mydbfile.mdf**</span><span class="sxs-lookup"><span data-stu-id="5e39d-208">**sqlmetal /dbml:mymeta.dbml mydbfile.mdf**</span></span>  
  
 <span data-ttu-id="5e39d-209">Generiert aus SQL Server Express eine DBML-Datei, die extrahierte SQL-Metadaten umfasst:</span><span class="sxs-lookup"><span data-stu-id="5e39d-209">Generate a .dbml file that includes extracted SQL metadata from SQL Server Express:</span></span>  
  
 <span data-ttu-id="5e39d-210">**sqlmetal /server:.\sqlexpress /dbml:mymeta.dbml /database:northwind**</span><span class="sxs-lookup"><span data-stu-id="5e39d-210">**sqlmetal /server:.\sqlexpress /dbml:mymeta.dbml /database:northwind**</span></span>  
  
 <span data-ttu-id="5e39d-211">Generiert Quellcode aus einer DBML-Metadatendatei:</span><span class="sxs-lookup"><span data-stu-id="5e39d-211">Generate source code from a .dbml metadata file:</span></span>  
  
 <span data-ttu-id="5e39d-212">**sqlmetal /namespace:nwind /code:nwind.cs /language:csharp mymetal.dbml**</span><span class="sxs-lookup"><span data-stu-id="5e39d-212">**sqlmetal /namespace:nwind /code:nwind.cs /language:csharp mymetal.dbml**</span></span>  
  
 <span data-ttu-id="5e39d-213">Generiert Quellcode direkt aus SQL-Metadaten:</span><span class="sxs-lookup"><span data-stu-id="5e39d-213">Generate source code from SQL metadata directly:</span></span>  
  
 <span data-ttu-id="5e39d-214">**sqlmetal /server:myserver /database:northwind /namespace:nwind /code:nwind.cs /language:csharp**</span><span class="sxs-lookup"><span data-stu-id="5e39d-214">**sqlmetal /server:myserver /database:northwind /namespace:nwind /code:nwind.cs /language:csharp**</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5e39d-215">Wenn Sie die Option **/pluralize** mit der Northwind-Beispieldatenbank verwenden, stellen Sie folgendes Verhalten fest.</span><span class="sxs-lookup"><span data-stu-id="5e39d-215">When you use the **/pluralize** option with the Northwind sample database, note the following behavior.</span></span> <span data-ttu-id="5e39d-216">Wenn SqlMetal Zeilentypnamen für Tabellen erstellt, wird für Tabellennamen die Singularform verwendet.</span><span class="sxs-lookup"><span data-stu-id="5e39d-216">When SqlMetal makes row-type names for tables, the table names are singular.</span></span> <span data-ttu-id="5e39d-217">Wenn <xref:System.Data.Linq.DataContext> -Eigenschaften für Tabellen erstellt werden, wird für Tabellennamen die Pluralform verwendet.</span><span class="sxs-lookup"><span data-stu-id="5e39d-217">When it makes <xref:System.Data.Linq.DataContext> properties for tables, the table names are plural.</span></span> <span data-ttu-id="5e39d-218">Zufällig treten die Tabellen in der Northwind-Beispieldatenbank bereits in Pluralform auf.</span><span class="sxs-lookup"><span data-stu-id="5e39d-218">Coincidentally, the tables in the Northwind sample database are already plural.</span></span> <span data-ttu-id="5e39d-219">Deshalb ist nicht erkennbar, dass dieser Schritt funktioniert.</span><span class="sxs-lookup"><span data-stu-id="5e39d-219">Therefore, you do not see that part working.</span></span> <span data-ttu-id="5e39d-220">Obwohl es üblich ist, Datenbanktabellen im Singular zu benennen, ist es in .NET auch verbreitet, Auflistungen in Pluralform zu benennen.</span><span class="sxs-lookup"><span data-stu-id="5e39d-220">Although it is common practice to name database tables singular, it is also a common practice in .NET to name collections plural.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e39d-221">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5e39d-221">See also</span></span>

- [<span data-ttu-id="5e39d-222">How to: (Vorgehensweise: Generieren des Objektmodells in Visual Basic oder C#)</span><span class="sxs-lookup"><span data-stu-id="5e39d-222">How to: Generate the Object Model in Visual Basic or C#</span></span>](../data/adonet/sql/linq/how-to-generate-the-object-model-in-visual-basic-or-csharp.md)
- [<span data-ttu-id="5e39d-223">Codegenerierung in LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="5e39d-223">Code Generation in LINQ to SQL</span></span>](../data/adonet/sql/linq/code-generation-in-linq-to-sql.md)
- [<span data-ttu-id="5e39d-224">External Mapping (Externe Zuordnung)</span><span class="sxs-lookup"><span data-stu-id="5e39d-224">External Mapping</span></span>](../data/adonet/sql/linq/external-mapping.md)

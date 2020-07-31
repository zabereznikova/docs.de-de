---
title: LINQ und Zeichenfolgen (C#)
description: LINQ kann Zeichenfolgen und Sammlungen von Zeichenfolgen abfragen und transformieren. Sie können LINQ-Abfragen mit C#-Zeichenfolgenfunktionen und regulären Ausdrücken vereinen.
ms.date: 07/20/2015
ms.assetid: dbe2d657-b3f3-487e-b645-21fb2d71cd7b
ms.openlocfilehash: c515a0c56ad6473f93c6339540e4ed0245bb5bd2
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165612"
---
# <a name="linq-and-strings-c"></a><span data-ttu-id="62aa3-104">LINQ und Zeichenfolgen (C#)</span><span class="sxs-lookup"><span data-stu-id="62aa3-104">LINQ and strings (C#)</span></span>

<span data-ttu-id="62aa3-105">LINQ kann zum Abfragen und Transformieren von Zeichenfolgen und Auflistungen von Zeichenfolgen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="62aa3-105">LINQ can be used to query and transform strings and collections of strings.</span></span> <span data-ttu-id="62aa3-106">Dieses Verfahren ist bei halbstrukturierten Daten in Textdateien besonders nützlich.</span><span class="sxs-lookup"><span data-stu-id="62aa3-106">It can be especially useful with semi-structured data in text files.</span></span> <span data-ttu-id="62aa3-107">LINQ-Abfragen können mit herkömmlichen Zeichenfolgenfunktionen und regulären Ausdrücken verbunden werden.</span><span class="sxs-lookup"><span data-stu-id="62aa3-107">LINQ queries can be combined with traditional string functions and regular expressions.</span></span> <span data-ttu-id="62aa3-108">Beispielsweise können Sie die Methode <xref:System.String.Split%2A?displayProperty=nameWithType> oder <xref:System.Text.RegularExpressions.Regex.Split%2A?displayProperty=nameWithType> verwenden, um ein Array von Zeichenfolgen zu erstellen, das Sie anschließend mit LINQ abfragen oder ändern können.</span><span class="sxs-lookup"><span data-stu-id="62aa3-108">For example, you can use the <xref:System.String.Split%2A?displayProperty=nameWithType> or <xref:System.Text.RegularExpressions.Regex.Split%2A?displayProperty=nameWithType> method to create an array of strings that you can then query or modify by using LINQ.</span></span> <span data-ttu-id="62aa3-109">Sie können die Methode <xref:System.Text.RegularExpressions.Regex.IsMatch%2A?displayProperty=nameWithType> in der `where`-Klausel einer LINQ-Abfrage verwenden.</span><span class="sxs-lookup"><span data-stu-id="62aa3-109">You can use the <xref:System.Text.RegularExpressions.Regex.IsMatch%2A?displayProperty=nameWithType> method in the `where` clause of a LINQ query.</span></span> <span data-ttu-id="62aa3-110">Sie können LINQ außerdem zum Abfragen und Ändern der <xref:System.Text.RegularExpressions.MatchCollection>-Ergebnisse, die von einem regulären Ausdruck zurückgegeben werden, verwenden.</span><span class="sxs-lookup"><span data-stu-id="62aa3-110">And you can use LINQ to query or modify the <xref:System.Text.RegularExpressions.MatchCollection> results returned by a regular expression.</span></span>

<span data-ttu-id="62aa3-111">Sie können auch die Techniken verwenden, die in diesem Abschnitt beschrieben werden, um halbstrukturierte Textdaten in XML zu transformieren.</span><span class="sxs-lookup"><span data-stu-id="62aa3-111">You can also use the techniques described in this section to transform semi-structured text data to XML.</span></span> <span data-ttu-id="62aa3-112">Weitere Informationen finden Sie unter [Vorgehensweise: Generieren von XML aus CSV-Dateien](how-to-generate-xml-from-csv-files.md).</span><span class="sxs-lookup"><span data-stu-id="62aa3-112">For more information, see [How to generate XML from CSV files](how-to-generate-xml-from-csv-files.md).</span></span>

<span data-ttu-id="62aa3-113">Die Beispiele in diesem Abschnitt gehören zu einer der folgenden beiden Kategorien:</span><span class="sxs-lookup"><span data-stu-id="62aa3-113">The examples in this section fall into two categories:</span></span>

## <a name="querying-a-block-of-text"></a><span data-ttu-id="62aa3-114">Abfragen eines Textblocks</span><span class="sxs-lookup"><span data-stu-id="62aa3-114">Querying a block of text</span></span>

<span data-ttu-id="62aa3-115">Sie können Textblöcke abfragen, analysieren und ändern, indem Sie sie mithilfe der <xref:System.String.Split%2A?displayProperty=nameWithType>- oder der <xref:System.Text.RegularExpressions.Regex.Split%2A?displayProperty=nameWithType>-Methode in ein abfragbares Array von kleineren Zeichenfolgen aufteilen.</span><span class="sxs-lookup"><span data-stu-id="62aa3-115">You can query, analyze, and modify text blocks by splitting them into a queryable array of smaller strings by using the <xref:System.String.Split%2A?displayProperty=nameWithType> method or the <xref:System.Text.RegularExpressions.Regex.Split%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="62aa3-116">Sie können den Quelltext in Wörter, Sätze, Absätze, Paragraphen, Seiten oder andere Kriterien unterteilen und anschließend andere Unterteilungen ausführen, wenn sie in Ihrer Abfrage benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="62aa3-116">You can split the source text into words, sentences, paragraphs, pages, or any other criteria, and then perform additional splits if they are required in your query.</span></span>

- [<span data-ttu-id="62aa3-117">Vorgehensweise: Zählen der Vorkommen eines Worts in einer Zeichenfolge (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="62aa3-117">How to count occurrences of a word in a string (LINQ) (C#)</span></span>](how-to-count-occurrences-of-a-word-in-a-string-linq.md)  
  <span data-ttu-id="62aa3-118">Zeigt die Verwendung von LINQ für einfache Textabfragen.</span><span class="sxs-lookup"><span data-stu-id="62aa3-118">Shows how to use LINQ for simple querying over text.</span></span>

- [<span data-ttu-id="62aa3-119">Vorgehensweise: Abfragen von Sätzen, die bestimmte Wörter enthalten (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="62aa3-119">How to query for sentences that contain a specified set of words (LINQ) (C#)</span></span>](how-to-query-for-sentences-that-contain-a-specified-set-of-words-linq.md)

  <span data-ttu-id="62aa3-120">Zeigt, wie Textdateien an beliebigen Grenzen unterteilt wird und wie Abfragen mit jedem Teil ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="62aa3-120">Shows how to split text files on arbitrary boundaries and how to perform queries against each part.</span></span>

- [<span data-ttu-id="62aa3-121">Vorgehensweise: Abfragen von Zeichen in einer Zeichenfolge (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="62aa3-121">How to query for characters in a string (LINQ) (C#)</span></span>](how-to-query-for-characters-in-a-string-linq.md)

  <span data-ttu-id="62aa3-122">Veranschaulicht, dass eine Zeichenfolge ein abfragbarer Typ ist.</span><span class="sxs-lookup"><span data-stu-id="62aa3-122">Demonstrates that a string is a queryable type.</span></span>

- [<span data-ttu-id="62aa3-123">Vorgehensweise: Kombinieren von LINQ-Abfragen mit regulären Ausdrücken (C#)</span><span class="sxs-lookup"><span data-stu-id="62aa3-123">How to combine LINQ queries with regular expressions (C#)</span></span>](how-to-combine-linq-queries-with-regular-expressions.md)

  <span data-ttu-id="62aa3-124">Zeigt, wie reguläre Ausdrücke in LINQ-Abfragen für komplexe Musterabgleiche bei gefilterten Abfrageergebnissen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="62aa3-124">Shows how to use regular expressions in LINQ queries for complex pattern matching on filtered query results.</span></span>

## <a name="querying-semi-structured-data-in-text-format"></a><span data-ttu-id="62aa3-125">Abfragen halbstrukturierter Daten im Textformat</span><span class="sxs-lookup"><span data-stu-id="62aa3-125">Querying semi-structured data in text format</span></span>

<span data-ttu-id="62aa3-126">Viele verschiedene Typen von Textdateien bestehen aus einer Reihe von Zeilen, die häufig mit ähnlicher Formatierung, z.B. durch Tabstopps oder Kommas getrennten Dateien oder Zeilen mit fester Länge.</span><span class="sxs-lookup"><span data-stu-id="62aa3-126">Many different types of text files consist of a series of lines, often with similar formatting, such as tab- or comma-delimited files or fixed-length lines.</span></span> <span data-ttu-id="62aa3-127">Nachdem Sie solch eine Textdatei in den Arbeitsspeicher gelesen haben, können Sie LINQ zum Abfragen bzw. Ändern der Zeilen verwenden.</span><span class="sxs-lookup"><span data-stu-id="62aa3-127">After you read such a text file into memory, you can use LINQ to query and/or modify the lines.</span></span> <span data-ttu-id="62aa3-128">LINQ-Abfragen vereinfachen zudem die Aufgabe, Daten aus mehreren Quellen zu kombinieren.</span><span class="sxs-lookup"><span data-stu-id="62aa3-128">LINQ queries also simplify the task of combining data from multiple sources.</span></span>

- [<span data-ttu-id="62aa3-129">Vorgehensweise: Suchen der Unterschiedsmenge zwischen zwei Listen (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="62aa3-129">How to find the set difference between two lists (LINQ) (C#)</span></span>](how-to-find-the-set-difference-between-two-lists-linq.md)

  <span data-ttu-id="62aa3-130">Zeigt, wie alle Zeichenfolgen gesucht werden, die in einer Liste, aber nicht in der anderen, vorhanden sind</span><span class="sxs-lookup"><span data-stu-id="62aa3-130">Shows how to find all the strings that are present in one list but not the other.</span></span>

- [<span data-ttu-id="62aa3-131">Vorgehensweise: Sortieren oder Filtern von Textdaten nach einem beliebigen Wort oder Feld (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="62aa3-131">How to sort or filter text data by any word or field (LINQ) (C#)</span></span>](how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)

  <span data-ttu-id="62aa3-132">Zeigt, wie Textzeilen anhand eines beliebigen Worts oder Felds sortiert werden.</span><span class="sxs-lookup"><span data-stu-id="62aa3-132">Shows how to sort text lines based on any word or field.</span></span>

- [<span data-ttu-id="62aa3-133">Vorgehensweise: Neuanordnen der Felder einer Datei mit Trennzeichen (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="62aa3-133">How to reorder the fields of a delimited file (LINQ) (C#)</span></span>](how-to-reorder-the-fields-of-a-delimited-file-linq.md)

  <span data-ttu-id="62aa3-134">Zeigt, wie Felder in einer Zeile in einer CSV-Datei neu angeordnet werden</span><span class="sxs-lookup"><span data-stu-id="62aa3-134">Shows how to reorder fields in a line in a .csv file.</span></span>

- [<span data-ttu-id="62aa3-135">Vorgehensweise: Verbinden und Vergleichen von Zeichenfolgenauflistungen (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="62aa3-135">How to combine and compare string collections (LINQ) (C#)</span></span>](how-to-combine-and-compare-string-collections-linq.md)

  <span data-ttu-id="62aa3-136">Zeigt, wie Zeichenfolgenlisten auf verschiedene Weise verbunden werden</span><span class="sxs-lookup"><span data-stu-id="62aa3-136">Shows how to combine string lists in various ways.</span></span>

- [<span data-ttu-id="62aa3-137">Vorgehensweise: Auffüllen von Objektsammlungen mit Daten aus mehreren Quellen (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="62aa3-137">How to populate object collections from multiple sources (LINQ) (C#)</span></span>](how-to-populate-object-collections-from-multiple-sources-linq.md)

  <span data-ttu-id="62aa3-138">Zeigt, wie Auflistungen erstellt werden, indem Sie mehrere Textdateien als Datenquellen verwenden</span><span class="sxs-lookup"><span data-stu-id="62aa3-138">Shows how to create object collections by using multiple text files as data sources.</span></span>

- [<span data-ttu-id="62aa3-139">Vorgehensweise: Verknüpfen des Inhalts unterschiedlicher Dateien (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="62aa3-139">How to join content from dissimilar files (LINQ) (C#)</span></span>](how-to-join-content-from-dissimilar-files-linq.md)
  
  <span data-ttu-id="62aa3-140">Zeigt, wie Zeichenfolgen in zwei Listen mit einem übereinstimmenden Schlüssel in einer einzigen Zeichenfolge vereint werden</span><span class="sxs-lookup"><span data-stu-id="62aa3-140">Shows how to combine strings in two lists into a single string by using a matching key.</span></span>

- [<span data-ttu-id="62aa3-141">Vorgehensweise: Teilen einer Datei in mehrere Dateien durch das Verwenden von Gruppen (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="62aa3-141">How to split a file into many files by using groups (LINQ) (C#)</span></span>](how-to-split-a-file-into-many-files-by-using-groups-linq.md)
  
  <span data-ttu-id="62aa3-142">Veranschaulicht, wie neue Dateien mithilfe einer einzelnen Datei als Datenquelle erstellt werden</span><span class="sxs-lookup"><span data-stu-id="62aa3-142">Shows how to create new files by using a single file as a data source.</span></span>

- [<span data-ttu-id="62aa3-143">Vorgehensweise: Berechnen von Spaltenwerten in einer CSV-Textdatei (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="62aa3-143">How to compute column values in a CSV text file (LINQ) (C#)</span></span>](how-to-compute-column-values-in-a-csv-text-file-linq.md)
  
  <span data-ttu-id="62aa3-144">Zeigt, wie mathematische Berechnungen bei Textdaten in CSV-Dateien ausgeführt werden</span><span class="sxs-lookup"><span data-stu-id="62aa3-144">Shows how to perform mathematical computations on text data in .csv files.</span></span>

## <a name="see-also"></a><span data-ttu-id="62aa3-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="62aa3-145">See also</span></span>

- [<span data-ttu-id="62aa3-146">Language Integrated Query (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="62aa3-146">Language-Integrated Query (LINQ) (C#)</span></span>](index.md)
- [<span data-ttu-id="62aa3-147">Generieren von XML aus CSV-Dateien</span><span class="sxs-lookup"><span data-stu-id="62aa3-147">How to generate XML from CSV files</span></span>](how-to-generate-xml-from-csv-files.md)

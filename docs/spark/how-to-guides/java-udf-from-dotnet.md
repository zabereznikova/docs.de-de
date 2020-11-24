---
title: Aufrufen benutzerdefinierter Java-Funktionen in .NET für Apache Spark-Anwendungen
description: In diesem Artikel erhalten Sie Informationen zum Aufrufen benutzerdefinierter Java-Funktionen in einer .NET für Apache Spark-Anwendung.
ms.author: nidutta
author: Niharikadutta
ms.date: 10/09/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: 17f0ff611e68a5dab2032f78ef75912f314d88a5
ms.sourcegitcommit: 34968a61e9bac0f6be23ed6ffb837f52d2390c85
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "94688266"
---
# <a name="call-a-java-udf-from-your-net-for-apache-spark-application"></a><span data-ttu-id="7fff2-103">Aufrufen benutzerdefinierter Java-Funktionen in .NET für Apache Spark-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="7fff2-103">Call a Java UDF from your .NET for Apache Spark application</span></span>

<span data-ttu-id="7fff2-104">In diesem Artikel erfahren Sie, wie Sie eine benutzerdefinierte Java-Funktion (User-Defined Function, UDF) in Ihrer [.NET für Apache Spark](https://github.com/dotnet/spark)-Anwendung aufrufen.</span><span class="sxs-lookup"><span data-stu-id="7fff2-104">In this article, you learn how to call a Java User-Defined Function (UDF) from your [.NET for Apache Spark](https://github.com/dotnet/spark) application.</span></span>

1. <span data-ttu-id="7fff2-105">Definieren Ihrer Java-UDFs und Kompilieren in das JAR-Format. Dieser Schritt ist nicht erforderlich, wenn Sie bereit über eine in einer JAR-Datei definierte UDF verfügen.</span><span class="sxs-lookup"><span data-stu-id="7fff2-105">How to define your Java UDFs and compile them into a jar - this step is not needed if you already have a UDF defined in a jar file.</span></span> <span data-ttu-id="7fff2-106">In diesem Fall benötigen Sie nur den vollständigen Namen der UDF-Funktion einschließlich des Pakets.</span><span class="sxs-lookup"><span data-stu-id="7fff2-106">In which case, all you need is the full name of the UDF function including the package.</span></span>
2. <span data-ttu-id="7fff2-107">Registrieren Sie Ihre Java-UDF, und rufen Sie sie in Ihrer .NET für Apache Spark-Anwendung auf.</span><span class="sxs-lookup"><span data-stu-id="7fff2-107">Register and call your Java UDF in your .NET for Apache Spark application.</span></span>

## <a name="define-and-compile-your-java-udfs"></a><span data-ttu-id="7fff2-108">Definieren und Kompilieren Ihrer Java-UDFs</span><span class="sxs-lookup"><span data-stu-id="7fff2-108">Define and compile your Java UDFs</span></span>

1. <span data-ttu-id="7fff2-109">Erstellen Sie ein Maven- oder SBT-Projekt, und fügen Sie in der Projektkonfigurationsdatei die folgenden Abhängigkeiten hinzu:</span><span class="sxs-lookup"><span data-stu-id="7fff2-109">Create a Maven or SBT project and add the following dependencies into the project configuration file:</span></span>
    1. `org.apache.spark.spark-core_2.11.<version>`
    2. `org.apache.spark.spark-sql_2.11.<version>`
2. <span data-ttu-id="7fff2-110">Definieren Sie Ihre Java-UDF, indem Sie entsprechend der Signatur Ihrer UDF die [relevante Schnittstelle](https://github.com/apache/spark/blob/master/sql/core/src/main/java/org/apache/spark/sql/api/java/UDF1.java) implementieren und das entsprechende Paket importieren. Sehen Sie sich dazu das nachstehende einfache Beispiel an.</span><span class="sxs-lookup"><span data-stu-id="7fff2-110">Define your Java UDF by implementing the [relevant interface](https://github.com/apache/spark/blob/master/sql/core/src/main/java/org/apache/spark/sql/api/java/UDF1.java) (according to your UDF's signature) and importing the relevant package as shown below in a simple example</span></span>

    ```java
    package com.ScalaUdf.app; // Name of package where UDF is defined
    import org.apache.spark.sql.api.java.UDF1; // UDF interface to implement

    public class JavaUdf implements UDF1<Integer, Integer> { // Name of the Java UDF
        private static final int serialVersionUID = 1;
        @Override
        public Integer call(Integer num) throws Exception { // Define logic of UDF
            return (num + 5);
        }
    }
    ```

3. <span data-ttu-id="7fff2-111">Kompilieren Sie Ihr Projekt, und packen Sie es, um eine ausführbare JAR-Datei zu erstellen, z. B. `UdfApp-0.0.1.jar`.</span><span class="sxs-lookup"><span data-stu-id="7fff2-111">Compile and package your project to create and executable jar say `UdfApp-0.0.1.jar`.</span></span>

## <a name="register-and-call-java-udfs-in-net-for-apache-spark"></a><span data-ttu-id="7fff2-112">Registrieren und Aufrufen von Java-UDFs in .NET für Apache Spark</span><span class="sxs-lookup"><span data-stu-id="7fff2-112">Register and call Java UDFs in .NET for Apache Spark</span></span>

1. <span data-ttu-id="7fff2-113">Verwenden Sie die [`RegisterJava`](https://github.com/dotnet/spark/blob/8dcdcdc7c60d5f42cba5a90f1346d854ab5bf7bb/src/csharp/Microsoft.Spark/Sql/UDFRegistration.cs#L424)-API, um Ihre Java-UDF mit Spark SQL zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="7fff2-113">Use the [`RegisterJava`](https://github.com/dotnet/spark/blob/8dcdcdc7c60d5f42cba5a90f1346d854ab5bf7bb/src/csharp/Microsoft.Spark/Sql/UDFRegistration.cs#L424) API to register your Java UDF with Spark SQL.</span></span>
2. <span data-ttu-id="7fff2-114">Registrieren Sie den Datenrahmen (`DataFrame`), für den Sie Ihre UDF als SQL-Tabelle mithilfe der [`CreateOrReplaceTempView`](https://github.com/dotnet/spark/blob/master/src/csharp/Microsoft.Spark/Sql/DataFrame.cs#L982)-Funktion aufrufen möchten.</span><span class="sxs-lookup"><span data-stu-id="7fff2-114">Register the `DataFrame` on which you want to call your UDF as an SQL Table using the [`CreateOrReplaceTempView`](https://github.com/dotnet/spark/blob/master/src/csharp/Microsoft.Spark/Sql/DataFrame.cs#L982) function.</span></span>
3. <span data-ttu-id="7fff2-115">Verwenden Sie `SparkSession.Sql`, um die UDF mithilfe von Spark SQL in der Tabellenansicht aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="7fff2-115">Use `SparkSession.Sql` to call the UDF on the table view using Spark SQL.</span></span>
<span data-ttu-id="7fff2-116">Unten finden Sie ein einfaches Beispiel, um die oben genannten Schritte zu veranschaulichen:</span><span class="sxs-lookup"><span data-stu-id="7fff2-116">A basic example to illustrate the above steps:</span></span>

    ```csharp
    class Program
    {
        static void Main()
        {
            SparkSession spark = SparkSession
                .Builder()
                .AppName("Scala/Java UDFs from .NET for Apache Spark")
                .GetOrCreate();
            spark.Udf().RegisterJava<int>("udfAdd5", "com.ScalaUdf.app.JavaUdf"); // Register your Java UDF as 'udfAdd5'
            DataFrame df = spark.CreateDataFrame(new int[] { 2, 5 });
            df.CreateOrReplaceTempView("numbersData"); // Create an SQL table from the DataFrame `df`
            DataFrame dfUdf = spark.Sql("SELECT udfAdd5(_1) As Result FROM numbersData"); // Call the registered UDF on the table
            dfUdf.Show();
            spark.Stop();
        }
    }
    ```

4. <span data-ttu-id="7fff2-117">Übermitteln Sie diese Anwendung mithilfe von `spark-submit`, indem Sie die zuvor kompilierte JAR-Datei der Java-UDF über die `--jars`-Option übergeben:</span><span class="sxs-lookup"><span data-stu-id="7fff2-117">Submit this application using `spark-submit` by passing the previously compiled Java UDF jar through the `--jars` option:</span></span>

    ```bash
    spark-submit --master local --jars UdfApp-0.0.1.jar --class org.apache.spark.deploy.dotnet.DotnetRunner microsoft-spark-2-4_2.11-1.0.0.jar InterRuntimeUDFs.exe
    ```

    <span data-ttu-id="7fff2-118">Für den daraus resultierenden `dfUdf`-Datenrahmen wurde in jeder Zeile der Eingabespalte wie von `JavaUdf` definiert die Nummer 5 hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="7fff2-118">The resultant `dfUdf` DataFrame had the number 5 added to each row of the input column as defined by `JavaUdf`:</span></span>

    ```text
    +-------+
    | Result|
    +-------+
    |      7|
    |     10|
    +-------+
    ```

## <a name="call-net-udf-from-scala-or-python-in-apache-spark"></a><span data-ttu-id="7fff2-119">Aufrufen einer .NET-UDF in Scala oder Python in Apache Spark</span><span class="sxs-lookup"><span data-stu-id="7fff2-119">Call .NET UDF from Scala or Python in Apache Spark</span></span>

<span data-ttu-id="7fff2-120">Sie können eine C#-UDF auch in einer Apache Spark-Anwendung, die in Scala oder Python geschrieben wurde, mithilfe des [Open-Source-Tools „sparkdotnetudf“](https://github.com/imback82/sparkdotnetudf) registrieren und aufrufen.</span><span class="sxs-lookup"><span data-stu-id="7fff2-120">You can also register and invoke a C# UDF from an Apache Spark application written in Scala or Python using [the sparkdotnetudf open source tool](https://github.com/imback82/sparkdotnetudf).</span></span>

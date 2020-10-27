---
title: Aufrufen benutzerdefinierter Java-Funktionen in .NET für Apache Spark-Anwendungen
description: In diesem Artikel erhalten Sie Informationen zum Aufrufen benutzerdefinierter Java-Funktionen in einer .NET für Apache Spark-Anwendung.
ms.author: nidutta
author: Niharikadutta
ms.date: 10/09/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: edf525102bf5503dcb51247b5fa590aa0d42b369
ms.sourcegitcommit: 67ebdb695fd017d79d9f1f7f35d145042d5a37f7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/20/2020
ms.locfileid: "92224115"
---
# <a name="call-a-java-udf-from-your-net-for-apache-spark-application"></a>Aufrufen benutzerdefinierter Java-Funktionen in .NET für Apache Spark-Anwendungen

In diesem Artikel erfahren Sie, wie Sie eine benutzerdefinierte Java-Funktion (User-Defined Function, UDF) in Ihrer [.NET für Apache Spark](https://github.com/dotnet/spark)-Anwendung aufrufen.

1. Definieren Ihrer Java-UDFs und Kompilieren in das JAR-Format. Dieser Schritt ist nicht erforderlich, wenn Sie bereit über eine in einer JAR-Datei definierte UDF verfügen. In diesem Fall benötigen Sie nur den vollständigen Namen der UDF-Funktion einschließlich des Pakets.
2. Registrieren Sie Ihre Java-UDF, und rufen Sie sie in Ihrer .NET für Apache Spark-Anwendung auf.

## <a name="define-and-compile-your-java-udfs"></a>Definieren und Kompilieren Ihrer Java-UDFs

1. Erstellen Sie ein Maven- oder SBT-Projekt, und fügen Sie in der Projektkonfigurationsdatei die folgenden Abhängigkeiten hinzu:
    1. `org.apache.spark.spark-core_2.11.<version>`
    2. `org.apache.spark.spark-sql_2.11.<version>`
2. Definieren Sie Ihre Java-UDF, indem Sie entsprechend der Signatur Ihrer UDF die [relevante Schnittstelle](https://github.com/apache/spark/blob/master/sql/core/src/main/java/org/apache/spark/sql/api/java/UDF1.java) implementieren und das entsprechende Paket importieren. Sehen Sie sich dazu das nachstehende einfache Beispiel an.

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

3. Kompilieren Sie Ihr Projekt, und packen Sie es, um eine ausführbare JAR-Datei zu erstellen, z. B. `UdfApp-0.0.1.jar`.

## <a name="register-and-call-java-udfs-in-net-for-apache-spark"></a>Registrieren und Aufrufen von Java-UDFs in .NET für Apache Spark

1. Verwenden Sie die [`RegisterJava`](https://github.com/dotnet/spark/blob/8dcdcdc7c60d5f42cba5a90f1346d854ab5bf7bb/src/csharp/Microsoft.Spark/Sql/UDFRegistration.cs#L424)-API, um Ihre Java-UDF mit Spark SQL zu registrieren.
2. Registrieren Sie den Datenrahmen (`DataFrame`), für den Sie Ihre UDF als SQL-Tabelle mithilfe der [`CreateOrReplaceTempView`](https://github.com/dotnet/spark/blob/master/src/csharp/Microsoft.Spark/Sql/DataFrame.cs#L982)-Funktion aufrufen möchten.
3. Verwenden Sie `SparkSession.Sql`, um die UDF mithilfe von Spark SQL in der Tabellenansicht aufzurufen.
Unten finden Sie ein einfaches Beispiel, um die oben genannten Schritte zu veranschaulichen:

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

4. Übermitteln Sie diese Anwendung mithilfe von `spark-submit`, indem Sie die zuvor kompilierte JAR-Datei der Java-UDF über die `--jars`-Option übergeben:

    ```bash
    spark-submit --master local --jars UdfApp-0.0.1.jar --class org.apache.spark.deploy.dotnet.DotnetRunner microsoft-spark-3.0.x-0.12.1.jar InterRuntimeUDFs.exe
    ```

    Für den daraus resultierenden `dfUdf`-Datenrahmen wurde in jeder Zeile der Eingabespalte wie von `JavaUdf` definiert die Nummer 5 hinzugefügt:

    ```text
    +-------+
    | Result|
    +-------+
    |      7|
    |     10|
    +-------+
    ```

## <a name="call-net-udf-from-scala-or-python-in-apache-spark"></a>Aufrufen einer .NET-UDF in Scala oder Python in Apache Spark

Sie können eine C#-UDF auch in einer Apache Spark-Anwendung, die in Scala oder Python geschrieben wurde, mithilfe des [Open-Source-Tools „sparkdotnetudf“](https://github.com/imback82/sparkdotnetudf) registrieren und aufrufen.

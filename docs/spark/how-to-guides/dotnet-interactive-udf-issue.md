---
title: Schreiben und Aufrufen von benutzerdefinierten Funktionen in interaktiven Umgebungen von .NET für Apache Spark
description: Hier erfahren Sie, wie Sie benutzerdefinierten Funktionen in interaktiven Shells von .NET für Apache Spark schreiben und aufrufen.
ms.author: nidutta
author: Niharikadutta
ms.date: 10/09/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: 8fb729a0b8220d15af641f916383bbd6146e2e33
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2020
ms.locfileid: "94441075"
---
# <a name="write-and-call-udfs-in-net-for-apache-spark-interactive-environments"></a>Schreiben und Aufrufen von benutzerdefinierten Funktionen in interaktiven Umgebungen von .NET für Apache Spark

In diesem Artikel erfahren Sie, wie Sie benutzerdefinierte Funktionen in einer interaktiven Umgebung von .NET für Apache Spark verwenden.

## <a name="prerequisites"></a>Voraussetzungen

1. Installation von [.NET Interactive](https://github.com/dotnet/interactive)
2. Installation von [Jupyter Lab](https://jupyter.org/)

## <a name="net-for-apache-spark-interactive-experience"></a>Interaktive Umgebung in .NET für Apache Spark

[.NET für Apache Spark](https://github.com/dotnet/spark) nutzt [.NET Interactive](https://devblogs.microsoft.com/dotnet/net-interactive-is-here-net-notebooks-preview-2/), um .NET-Unterstützung für die interaktive Umgebung in Spark bereitzustellen. Informationen zum Einrichten der Umgebung zum Testen von .NET Interactive mit Jupyter Notebook finden Sie im [.NET Interactive-Repository](https://github.com/dotnet/interactive).

Es wird außerdem empfohlen, [diesen Artikel über die Serialisierung von benutzerdefinierten Funktionen in .NET für Apache Spark](udf-guide.md) zu lesen, um zu erfahren, was benutzerdefinierte Funktionen sind und wie diese in .NET für Apache Spark serialisiert werden.
In diesem Leitfaden wird Jupyter Notebook verwenden, um die Verwendung von benutzerdefinierten Funktionen in einer interaktiven Umgebung zu veranschaulichen.

## <a name="define-a-udf-in-net-interactive"></a>Definieren einer benutzerdefinierten Funktion in .NET Interactive

In der interaktiven Umgebung können Sie sich eine Zelle als den Codeausschnitt vorstellen, der im Rahmen einer [REPL](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop)-Iteration übermittelt wird. Sehen Sie sich beispielsweise das folgende Notebook an:

![Jupyter Notebook-Zellen](./media/dotnet-interactive/dotnet-interactive-cells.png)

Jeder mit einem roten Pfeil gekennzeichnete Block ist eine Zelle bzw. eine Übermittlung von Code an Spark. Wenn jetzt eine benutzerdefinierte Funktion definiert wird, die auf ein benutzerdefiniertes Objekt verweist, ist erforderlich, dass die benutzerdefinierte Funktion in derselben Zelle definiert wird, in der sich das Objekt befindet, auf das verwiesen wird. Dies wird im folgenden Beispiel veranschaulicht:

![Funktionierende benutzerdefinierte Funktion](./media/dotnet-interactive/working-udf.png)

## <a name="call-a-udf-on-a-dataframe"></a>Aufrufen einer benutzerdefinierten Funktion für ein DataFrame

Beim Aufrufen einer zuvor definierten benutzerdefinierten Funktion für ein `DataFrame` ist es wichtig, dass sichergestellt wird, dass die benutzerdefinierte Funktion in einer zuvor übermittelten Zelle definiert wurde, bevor sie aufgerufen wird. Dies sehen Sie im vorherigen Beispiel.

Als Nächstes sehen Sie, was geschieht, wenn die benutzerdefinierte Funktion in der gleichen Zelle aufgerufen wird, in der sie definiert wird.

![Fehler bei Aufruf einer benutzerdefinierten Funktion](./media/dotnet-interactive/udf_fails.png)

Der oben hervorgehobene Fehler wird dadurch verursacht, dass die Assemblys der benutzerdefinierten Funktion zunächst kompiliert und an die Worker übermittelt werden müssen, bevor sie für ein DataFrame aufgerufen werden kann.

Es gibt einige wichtige Dinge, die Sie beim Implementieren von benutzerdefinierten Funktionen in interaktiven Umgebungen von .NET für Apache Spark beachten müssen (z. B. [Azure Synapse-Notebooks](/azure/synapse-analytics/spark/apache-spark-development-using-notebooks)).

## <a name="faqs"></a>Häufig gestellte Fragen

1. **Wieso führt der Verweis eines benutzerdefinierten Objekts durch meine benutzerdefinierte Funktion zu einem Fehler`Type Submission#_ is not marked as serializable`?**
    .NET Interactive umschließt alle Zellen mit einer Wrapperklasse der Zellenübermittlungsnummer, um alle übermittelten Zellen eindeutig zu identifizieren. Wie in [diesem Leitfaden](udf-guide.md) ausführlich erläutert wurde, wird das Ziel einer benutzerdefinierten Funktion, die auf ein benutzerdefiniertes Objekt verweist, das serialisiert wird, in die Serialisierung eingeschlossen. Diese wird bei .NET Interactive durch die Wrapperklasse der Zelle umschlossen, in der das benutzerdefinierte Objekt definiert wird.
    Als Nächstes sehen Sie sich an, wie sich dies auf die Definition der benutzerdefinierten Funktion im Notebook auswirkt:

    ![Serialisierungsfehler der benutzerdefinierten Funktion](./media/dotnet-interactive/udf-serialization-error.png)

    Wie bei `udf2_fails` zu sehen ist, wird die Fehlermeldung mit dem Text „Type `Submission#7`“ nicht als serialisierbar gekennzeichnet. Das liegt daran, dass .NET Interactive alle in einer Zelle definierten Objekte mit der `Submission#`-Klasse umschließt, die bei Bedarf generiert wird und daher nicht mit `Serializable` gekennzeichnet wird.

    Aus diesem Grund ist es **erforderlich, dass eine benutzerdefinierte Funktion, die auf ein benutzerdefiniertes Objekt verweist, in derselben Zelle wie das Objekt definiert wird**.

2. **Wieso funktionieren Broadcastvariablen nicht in .NET Interactive?**
    Broadcastvariablen funktionieren aufgrund der zuvor genannten Gründe nicht in .NET Interactive. Es empfiehlt sich, [diesen Leitfaden zu Broadcastvariablen](broadcast-guide.md) zu lesen, um ein besseres Verständnis darüber zu erlangen, was Broadcastvariablen sind und wie sie verwendet werden. Broadcastvariablen funktionieren in interaktiven Szenarios aufgrund des Entwurfs von .NET Interactive nicht, bei dem einzelnen in einer Zelle definierten Objekten die Zellenübermittlungsklasse angefügt wird. Dies führt zur zuvor gezeigten Ausnahme, da die Klasse nicht als serialisierbar gekennzeichnet ist.
    Im Folgenden wird das folgende Beispiel untersucht:

    ![Fehler bei Broadcastvariablen](./media/dotnet-interactive/broadcast-fails.png)

    Wie in den vorherigen Abschnitten empfohlen werden sowohl die benutzerdefinierte Funktion als auch das Objekt, auf das verwiesen wird (in diesem Fall eine Broadcastvariable), in derselben Zelle definiert. Allerdings wird dennoch der `SerializationException`-Fehler ausgelöst, der angibt, dass `Microsoft.Spark.Sql.Session` nicht als serialisierbar markiert wurde. Das liegt daran, dass der Compiler versucht, das Broadcastvariablenobjekt `bv` zu serialisieren, aber ermittelt, dass das `spark`-Objekt [`SparkSession`](https://github.com/dotnet/spark/blob/master/src/csharp/Microsoft.Spark/Sql/SparkSession.cs#L20) an den Namen angefügt ist, das als serialisierbar gekennzeichnet werden muss. Dies kann durch einen Blick in die dekompilierte Assembly dieser Zellenübermittlung einfacher veranschaulicht werden:

    ![Dekompilierter Assemblycode](./media/dotnet-interactive/decompiledAssembly.png)

    Wenn Sie die [`SparkSession`](https://github.com/dotnet/spark/blob/master/src/csharp/Microsoft.Spark/Sql/SparkSession.cs#L20)-Klasse mit `[Serializable]` kennzeichnen, kann dies funktionieren. Dabei handelt es sich jedoch um keine ideale Lösung, da Sie dem Benutzer nicht die Fähigkeit verleihen möchten, ein SparkSession-Objekt zu serialisieren, was zu einem seltsamen und unerwünschten Verhalten führen kann. Hierbei handelt es sich um ein [bekanntes Problem](https://github.com/dotnet/spark/issues/619), das in zukünftigen Versionen gelöst wird.

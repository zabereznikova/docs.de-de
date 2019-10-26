---
title: Beispiel für LINQ to XML Datenbindung
ms.date: 10/22/2019
ms.topic: sample
helpviewer_keywords:
- linq to xml data binding sample
ms.openlocfilehash: aac814e4768a863a93e69e34cd18c941a9b35c89
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2019
ms.locfileid: "72921221"
---
# <a name="linq-to-xml-data-binding-sample"></a>Beispiel für LINQ to XML Datenbindung

In diesem Artikel wird das LinqToXmlDataBinding-Beispiel beschrieben, eine Windows Presentation Foundation-app (WPF), die Benutzeroberflächen Komponenten an eine eingebettete XML-Datenquelle bindet.

## <a name="overview"></a>Übersicht

Das LinqToXmlDataBinding-Beispiel ist eine Windows Presentation Foundation-app (WPF) C# , die-und XAML-Quelldateien enthält. Ein eingebettetes XML-Dokument definiert eine Liste von Büchern. Die APP ermöglicht dem Benutzer, die Buch Einträge anzuzeigen, hinzuzufügen, zu löschen und zu bearbeiten.

Es gibt zwei primäre Quelldateien:

- [L2DBForm.xaml](l2dbform-xaml-source-code.md) enthält den XAML-Deklarationscode für die Benutzeroberfläche des Hauptfensters. Sie enthält außerdem einen Abschnitt mit einer Fenster Ressource, in dem ein Datenanbieter und ein eingebettetes XML-Dokument für die Buch Listen definiert sind.

- [L2DBForm.xaml.cs](l2dbform-xaml-cs-source-code.md) enthält die Initialisierungs- und Ereignisbehandlungsmethoden, die der Benutzeroberfläche zugeordnet sind.

Das Hauptfenster ist in die folgenden vier vertikalen Benutzeroberflächenabschnitte unterteilt:

- **XML**: Zeigt die unformatierte XML-Quelle der eingebetteten Bücherliste an.

- **Book List** (Bücherliste): Zeigt die Bucheinträge als Standardtext an, und versetzt den Benutzer in die Lage, einzelne Einträge auszuwählen und zu löschen.

- **Edit Selected Book** (Ausgewähltes Buch bearbeiten): Ermöglicht es dem Benutzer, die dem aktuell ausgewählten Bucheintrag zugeordneten Werte zu bearbeiten.

- **Add New Book** (Neues Buch hinzufügen): Ermöglicht das Erstellen eines neuen Bucheintrags anhand der vom Benutzer eingegebenen Werte.

## <a name="run-the-sample"></a>Ausführen des Beispiels

In diesem Abschnitt wird gezeigt, wie Sie das LinqToXmlDataBinding-Projekt in Visual Studio erstellen und erstellen und wie Sie die resultierende LinqToXmlDataBinding-Windows Presentation Foundation (WPF)-app ausführen.

### <a name="create-the-project"></a>Erstellen eines Projekts

1. Starten Sie Visual Studio, und erstellen Sie eine C#-**WPF-App** mit dem Namen **LinqToXmlDataBinding**.

   Das Projekt muss .NET Framework 3.5 (oder höher) verwenden.

1. Sofern nicht bereits vorhanden, fügen Sie Projektverweise für die folgenden .NET-Assemblys hinzu:

    - <legacyBold>System.Data</legacyBold>
    - System.Data.DataSetExtensions
    - System.Xml
    - System.Xml

1. Erstellen Sie die Projektmappe, indem Sie **STRG**+**UMSCHALTTASTE**+**B** drücken, und führen Sie sie dann mit **F5** aus.

   Das Projekt sollte ohne Fehler kompiliert und als generische WPF-Anwendung ausgeführt werden.

### <a name="add-code"></a>Code hinzufügen

1. Benennen Sie im **Projektmappen-Explorer** die Quelldatei **Window1.xaml** in **L2XDBForm.xaml** um.

   Die abhängige Quelldatei Window1.XAML.cs wird automatisch in L2XDBForm.XAML.cs umbenannt.

1. Ersetzen Sie den Quellcode in der Datei **L2XDBForm. XAML** durch den [Quellcode L2DBForm. XAML](l2dbform-xaml-source-code.md). Verwenden Sie zum Arbeiten mit dieser Datei die XAML-Quellansicht.

1. Ersetzen Sie auch die Quelle in **L2XDBForm.XAML.cs** durch den [L2DBForm.XAML.cs-Quellcode](l2dbform-xaml-cs-source-code.md).

1. Ersetzen Sie in der Datei **app. XAML**alle Vorkommen der Zeichenfolge **Window1. XAML** durch **L2XDBForm. XAML**.

1. Erstellen Sie die Projektmappe, indem Sie **STRG**+**UMSCHALTTASTE**+**B** drücken.

### <a name="run-the-app"></a>Ausführen der App

Die LinqToXmlDataBinding-App ermöglicht dem Benutzer, eine Liste von Büchern anzuzeigen und zu bearbeiten, die als eingebettetes XML-Element gespeichert ist. Führen Sie die APP aus, indem Sie **F5** drücken (Debuggen starten) oder **STRG**+**F5** (Starten ohne Debugging).

Daraufhin wird ein Programmfenster mit dem Titel **WPF-Datenbindung mit LINQ to XML** angezeigt.

Im obersten Abschnitt der Benutzeroberfläche wird das unformatierte **XML** angezeigt, das die Buchliste darstellt. Die Anzeige erfolgt unter Verwendung eines WPF-<xref:System.Windows.Controls.TextBlock>-Steuerelements, das keine Interaktion mithilfe von Maus oder Tastatur zulässt.

Im zweiten vertikalen Abschnitt mit der Bezeichnung **Book List** (Buchliste) werden die Bücher als geordnete Nur-Text-Liste angezeigt. Dazu wird ein <xref:System.Windows.Controls.ListBox>-Steuerelement verwendet, das die Auswahl über Maus oder Tastatur zulässt.

### <a name="add-and-delete-books"></a>Bücher hinzufügen und löschen

Wenn Sie der Liste ein neues Buch hinzufügen möchten, geben Sie im Abschnitt **ID** und **Wert** <xref:System.Windows.Controls.TextBox>-Steuerelemente im letzten Abschnitt, **Add New Book**, Werte ein, und wählen Sie dann **Book hinzufügen**aus. Das Buch wird in der Liste der Buch-und XML-Auflistungen an die Liste angefügt. Das Programm prüft die Eingabewerte nicht auf ihre Gültigkeit.

Wenn Sie ein vorhandenes Buch aus der Liste löschen möchten, wählen Sie es im Abschnitt **Book List** aus, und wählen Sie dann **Ausgewähltes Buch entfernen**aus. Der Bucheintrag wird aus dem Buch und den unformatierten XML-Quell Auflistungen entfernt.

### <a name="edit-a-book-entry"></a>Bucheintrag bearbeiten

1. Wählen Sie den Bucheintrag im zweiten Abschnitt, **Book List**, aus.

   Die aktuellen Werte werden im Abschnitt **Edit Selected Book** angezeigt.

1. Bearbeiten Sie die Werte mit der Tastatur. Sobald das <xref:System.Windows.Controls.TextBox>-Steuerelement den Fokus verliert, werden Änderungen automatisch an die XML-Quell-und-Buch Auflistungen weitergegeben.

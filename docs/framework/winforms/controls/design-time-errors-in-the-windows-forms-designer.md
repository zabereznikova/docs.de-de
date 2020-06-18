---
title: Entwurfs Zeitfehler im Windows Forms-Designer
titleSuffix: ''
description: Erfahren Sie mehr über die Fehler, die auftreten, wenn das Windows Forms-Designer aufgrund eines Fehlers im Code, in einer Drittanbieter Komponente oder an einer anderen Stelle nicht geladen werden kann.
ms.date: 09/09/2019
f1_keywords:
- DTELErrorList
- WhyDTELPage
helpviewer_keywords:
- errors [Windows Forms Designer]
- design-time errors [Windows Forms Designer]
ms.assetid: ad408380-825a-46d8-9a4a-531b130b88ce
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: d9c3993dfce9312c3271c499b6c0cd0c11253ca8
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2020
ms.locfileid: "84904389"
---
# <a name="windows-forms-designer-error-page"></a>Windows Forms-Designer Fehlerseite

Wenn das Windows Forms-Designer aufgrund eines Fehlers im Code, in einer Drittanbieter Komponente oder an einem anderen Ort nicht geladen werden kann, wird anstelle des Designers eine Fehlerseite angezeigt. Diese Fehlerseite weist nicht notwendigerweise auf einen Fehler im Designer hin. Der Fehler kann sich auf der Code Behind-Seite mit dem Namen befinden \<your-form-name> . Designer.cs. Fehler werden in redusible, gelben Balken mit einem Link angezeigt, um zum Speicherort des Fehlers auf der Codepage zu springen.

![Windows Forms-Designer Fehlerseite](media/windows-forms-designer-error-page-collapsed.png)

Sie können die Fehler ignorieren und mit dem Laden des Designers fortfahren, indem Sie auf **ignorieren und Fortfahren**klicken. Diese Aktion kann zu unerwartetem Verhalten führen, z. b. werden Steuerelemente möglicherweise nicht auf der Entwurfs Oberfläche angezeigt.

## <a name="instances-of-this-error"></a>Instanzen dieses Fehlers

Wenn die gelbe Fehler Leiste erweitert wird, wird jede Instanz des Fehlers aufgelistet. Viele Fehlertypen enthalten eine genaue Position im folgenden Format: *[Projektname]* *[Formular Name]* Zeile:*[Zeilennummer]* Spalte:*[Spaltennummer]*. Wenn dem Fehler eine aufrufsstapel zugeordnet ist, können Sie auf den Link zum **Anzeigen der Telefon** Verbindung klicken, um ihn anzuzeigen. Wenn Sie die-aufrufsstapel untersuchen, können Sie den Fehler weiter beheben.

![Windows Forms-Designer erweiterter Fehler](media/windows-forms-designer-error-page-expanded.png)

> [!NOTE]
>
> - Bei Visual Basic-apps zeigt die Seite Entwurfszeit Fehler nicht mehr als einen Fehler an, es werden jedoch möglicherweise mehrere Instanzen desselben Fehlers angezeigt.
> - Für C++-apps haben Fehler keine Code Speicherort Verknüpfungen.

## <a name="help-with-this-error"></a>Hilfe zu diesem Fehler

Wenn ein Hilfethema für den Fehler verfügbar ist, klicken Sie auf den Link **MSDN Help** , um direkt zur Hilfeseite auf docs.Microsoft.com zu navigieren.

## <a name="forum-posts-about-this-error"></a>Forumbeiträge zu diesem Fehler

Klicken Sie auf den Link **MSDN-Foren nach Beiträgen zu diesem Fehler durchsuchen** , um zu den Microsoft Developer Network-Foren zu navigieren. Möglicherweise möchten Sie die [Windows Forms-Designer](https://social.msdn.microsoft.com/Forums/windows/home?forum=winformsdesigner) -oder [Windows Forms](https://social.msdn.microsoft.com/Forums/windows/home?category=windowsforms) Foren genauer durchsuchen.

## <a name="design-time-errors"></a>Entwurfs Zeitfehler

In diesem Abschnitt werden einige der Fehler aufgelistet, auf die Sie möglicherweise stoßen.

### <a name="identifier-name-is-not-a-valid-identifier"></a>" \<identifier name> " ist kein gültiger Bezeichner.

Dieser Fehler weist darauf hin, dass ein Feld, eine Methode, ein Ereignis oder ein Objekt nicht ordnungsgemäß benannt ist.

### <a name="name-already-exists-in-project-name"></a>" \<name> " ist bereits in " \<project name> " vorhanden.

Fehlermeldung: "'" ist \<name> bereits in "" vorhanden \<project name> . Geben Sie einen eindeutigen Namen ein. "

Sie haben einen Namen für ein geerbtes Formular angegeben, das bereits im Projekt vorhanden ist. Um diesen Fehler zu beheben, müssen Sie der geerbten Form einen eindeutigen Namen einräumen.

### <a name="toolbox-tab-name-is-not-a-toolbox-category"></a>" \<Toolbox tab name> " ist keine Toolbox Kategorie.

Ein Drittanbieter-Designer hat versucht, auf eine Registerkarte in der Toolbox zuzugreifen, die nicht vorhanden ist. Wenden Sie sich an den Komponentenhersteller.

### <a name="a-requested-language-parser-is-not-installed"></a>Ein erforderlicher Sprachenparser wurde nicht installiert

Fehlermeldung: "ein angeforderter sprach Parser ist nicht installiert. Der Name des Sprachen Parsers ist " {0} ".

Visual Studio hat versucht, einen Designer zu laden, der für den Dateityp registriert ist, dies ist jedoch nicht möglich. Dies liegt wahrscheinlich daran, dass während des Setups ein Fehler aufgetreten ist. Wenden Sie sich an den Hersteller der Sprache, mit der Sie eine Korrektur durcharbeiten.

### <a name="a-service-required-for-generating-and-parsing-source-code-is-missing"></a>Ein zum Generieren und Verarbeiten des Quellcodes erforderlicher Dienst ist nicht vorhanden

Dies ist ein Problem mit einer Drittanbieter Komponente. Wenden Sie sich an den Komponentenhersteller.

### <a name="an-exception-occurred-while-trying-to-create-an-instance-of-object-name"></a>Ausnahme beim Erstellen einer Instanz von " \<object name> ".

Fehlermeldung: "beim Versuch, eine Instanz von ' ' zu erstellen, ist eine Ausnahme aufgetreten \<object name> . Ausnahme \<exception string\> : "".

Ein Drittanbieter-Designer hat angefordert, dass Visual Studio ein Objekt erstellt, aber das Objekt hat einen Fehler ausgelöst. Wenden Sie sich an den Komponentenhersteller.

### <a name="another-editor-has-document-name-open-in-an-incompatible-mode"></a>Ein anderer Editor hat " \<document name> " in einem inkompatiblen Modus geöffnet.

Fehlermeldung: "in einem anderen Editor ist ' \<document name> ' in einem inkompatiblen Modus geöffnet. Schließen Sie den Editor, und wiederholen Sie den Vorgang. "

Dieser Fehler tritt auf, wenn Sie versuchen, eine Datei zu öffnen, die bereits in einem anderen Editor geöffnet ist. Der Editor, für den die Datei bereits geöffnet ist, wird angezeigt. Um diesen Fehler zu beheben, schließen Sie den Editor, in dem die Datei geöffnet ist, und wiederholen Sie den Vorgang.

### <a name="another-editor-has-made-changes-to-document-name"></a>Ein anderer Editor hat Änderungen an " \<document name> " vorgenommen.

Schließen Sie den Designer, und öffnen Sie ihn erneut, damit die Änderungen wirksam werden. Normalerweise lädt Visual Studio einen Designer automatisch erneut, nachdem Änderungen vorgenommen wurden. Andere Designer, wie z. b. Komponenten-Designer von Drittanbietern, unterstützen jedoch möglicherweise das Neuladen Verhalten nicht. In diesem Fall werden Sie von Visual Studio aufgefordert, den Designer manuell zu schließen und erneut zu öffnen.

### <a name="another-editor-has-the-file-open-in-an-incompatible-mode"></a>Die Datei ist in einem anderen Editor in einem inkompatiblen Modus geöffnet

Fehlermeldung: "die Datei wird von einem anderen Editor in einem inkompatiblen Modus geöffnet. Schließen Sie den Editor, und wiederholen Sie den Vorgang. "

Diese Meldung ähnelt der Meldung "in einem anderen Editor ist ' \<document name> ' in einem inkompatiblen Modus geöffnet", aber der Dateiname kann von Visual Studio nicht bestimmt werden. Um diesen Fehler zu beheben, schließen Sie den Editor, in dem die Datei geöffnet ist, und wiederholen Sie den Vorgang.

### <a name="array-rank-rank-in-array-is-too-high"></a>Der Array Rang " \<rank in array> " ist zu hoch.

Visual Studio unterstützt nur Einzel Dimensions Arrays in dem Codeblock, der vom Designer analysiert wird. Mehrdimensionale Arrays sind außerhalb dieses Bereichs gültig.

### <a name="assembly-assembly-name-could-not-be-opened"></a>Die Assembly " \<assembly name> " konnte nicht geöffnet werden.

Fehlermeldung: "Assembly" \<assembly name> konnte nicht geöffnet werden. Vergewissern Sie sich, dass die Datei noch vorhanden ist. "

Diese Fehlermeldung wird angezeigt, wenn Sie versuchen, eine Datei zu öffnen, die nicht geöffnet werden konnte. Vergewissern Sie sich, dass die Datei vorhanden ist und eine gültige Assembly ist.

### <a name="bad-element-type-this-serializer-expects-an-element-of-type-type-name"></a>Ungültiger Elementtyp. Dieses Serialisierungsprogramm erwartet ein Element vom Typ " \<type name> ".

Dies ist ein Problem mit einer Drittanbieter Komponente. Wenden Sie sich an den Komponentenhersteller.

### <a name="cannot-access-the-visual-studio-toolbox-at-this-time"></a>Auf die Visual Studio-Toolbox kann derzeit nicht zugegriffen werden

Visual Studio hat einen aufzurufenden Toolbox aufgerufen, der nicht verfügbar war. Wenn dieser Fehler angezeigt wird, melden Sie sich, wenn dieser Fehler angezeigt wird, mit " [Problem melden](/visualstudio/ide/how-to-report-a-problem-with-visual-studio)" an.

### <a name="cannot-bind-an-event-handler-to-the-event-name-event-because-it-is-read-only"></a>Ein Ereignishandler kann nicht an das Ereignis "" gebunden werden, \<event name> da er schreibgeschützt ist.

Dieser Fehler tritt am häufigsten auf, wenn Sie versucht haben, ein Ereignis mit einem Steuerelement zu verbinden, das von einer Basisklasse geerbt wurde. Wenn die Member-Variable des Steuer Elements privat ist, kann Visual Studio das Ereignis nicht mit der-Methode verbinden. An private geerbte Steuerelemente können keine zusätzlichen Ereignisse gebunden werden.

### <a name="cannot-create-a-method-name-for-the-requested-component-because-it-is-not-a-member-of-the-design-container"></a>Für die angeforderte Komponente kann kein Methodenname erstellt werden, da sie kein Member des Entwurfscontainers ist

Visual Studio hat versucht, einen Ereignishandler zu einer Komponente hinzuzufügen, die im Designer nicht über eine Member-Variable verfügt. Wenden Sie sich an den Komponentenhersteller.

### <a name="cannot-name-the-object-name-because-it-is-already-named-name"></a>Der Name des Objekts ' ' kann nicht benannt werden, \<name> da es bereits ' ' heißt. \<name>

Dies ist ein interner Fehler im Visual Studio-Serialisierungsprogramm. Gibt an, dass das Serialisierungsprogramm versucht hat, ein Objekt zweimal zu benennen, was nicht unterstützt wird. Wenn dieser Fehler angezeigt wird, melden Sie sich mit " [Problem melden](/visualstudio/ide/how-to-report-a-problem-with-visual-studio)" an.

### <a name="cannot-remove-or-destroy-inherited-component-component-name"></a>Geerbte Komponente "" kann nicht entfernt oder zerstört werden. \<component name>

Geerbte Steuerelemente sind im Besitz ihrer vererbenden Klasse. Änderungen am geerbten Steuerelement müssen in der Klasse vorgenommen werden, von der das Steuerelement stammt. Daher können Sie Sie nicht umbenennen oder zerstören.

### <a name="category-toolbox-tab-name-does-not-have-a-tool-for-class-class-name"></a>Die Kategorie ' ' \<Toolbox tab name> weist kein Tool für die-Klasse auf. \<class name>

Der Designer hat versucht, auf eine Klasse auf einer bestimmten Toolbox Registerkarte zu verweisen, die Klasse ist jedoch nicht vorhanden. Wenden Sie sich an den Komponentenhersteller.

### <a name="class-class-name-has-no-matching-constructor"></a>Die Klasse ' \<class name> ' weist keinen passenden Konstruktor auf.

Ein Designer von Drittanbietern hat Visual Studio aufgefordert, ein Objekt mit bestimmten Parametern im Konstruktor zu erstellen, das nicht vorhanden ist. Wenden Sie sich an den Komponentenhersteller.

### <a name="code-generation-for-property-property-name-failed"></a>Fehler bei der Code Generierung für die Eigenschaft " \<property name> ".

Dies ist ein generischer Wrapper für einen Fehler. Die Fehler Zeichenfolge, die diese Meldung begleitet, enthält weitere Details zur Fehlermeldung und einen Link zu einem spezifischeren Hilfethema. Beheben Sie diesen Fehler, indem Sie den in der Fehlermeldung angegebenen Fehler beheben.

### <a name="component-component-name-did-not-call-containeradd-in-its-constructor"></a>Die Komponente " \<component name> " hat im Konstruktor "Container. Add ()" nicht aufgerufen.

Dies ist ein Fehler in der Komponente, die Sie soeben geladen oder im Formular abgelegt haben. Gibt an, dass sich die Komponente nicht selbst dem Container Steuerelement hinzugefügt hat (unabhängig davon, ob dies ein anderes Steuerelement oder ein Formular ist). Der Designer ist weiterhin funktionsfähig, aber es treten möglicherweise Probleme mit der Komponente zur Laufzeit auf.

Wenden Sie sich an den Hersteller der Komponente, um den Fehler zu beheben. Oder wenn es sich um eine von Ihnen erstellte Komponente handelt, müssen Sie die `IContainer.Add` -Methode im Konstruktor der Komponente aufzurufen.

### <a name="component-name-cannot-be-empty"></a>Der Komponentenname darf nicht leer sein

Dieser Fehler tritt auf, wenn Sie versuchen, eine Komponente in einen leeren Wert umzubenennen.

### <a name="could-not-access-the-variable-variable-name-because-it-has-not-been-initialized-yet"></a>Auf die Variable "" konnte nicht zugegriffen werden, \<variable name> da Sie noch nicht initialisiert wurde.

Dieser Fehler kann aufgrund von zwei Szenarios auftreten. Der Drittanbieter eines Drittanbieters hat ein Problem mit einem Steuerelement oder einer Komponente, die Sie verteilt haben, oder der geschriebene Code weist rekursive Abhängigkeiten zwischen Komponenten auf.

Stellen Sie sicher, dass der Code keine rekursive Abhängigkeit hat, um diesen Fehler zu beheben. Wenn dies nicht der Fall ist, notieren Sie den genauen Text der Fehlermeldung, und wenden Sie sich an den Hersteller der Komponente.

### <a name="could-not-find-type-type-name"></a>Der Typ "" wurde nicht gefunden. \<type name>

Fehlermeldung: "der Typ" "wurde nicht gefunden \<type name> . Stellen Sie sicher, dass auf die Assembly, die diesen Typ enthält, verwiesen wird. Wenn dieser Typ Teil des Entwicklungsprojekts ist, stellen Sie sicher, dass das Projekt erfolgreich erstellt wurde. "

Dieser Fehler ist aufgetreten, weil kein Verweis gefunden wurde. Stellen Sie sicher, dass auf den in der Fehlermeldung aufgeführten Typ verwiesen wird und dass alle Assemblys, die der Typ erfordert, ebenfalls referenziert werden. Häufig besteht das Problem darin, dass ein Steuerelement in der Projekt Mappe nicht erstellt wurde. Wählen Sie zum Erstellen im Menü **Erstellen** die Option Projekt Mappe **Erstellen** aus. Wenn das Steuerelement bereits erstellt wurde, fügen Sie einen Verweis manuell aus dem Kontextmenü des Ordners " **Verweise** " oder " **Abhängigkeiten** " in Projektmappen-Explorer hinzu.

### <a name="could-not-load-type-type-name"></a>Der Typ "" konnte nicht geladen werden. \<type name>

Fehlermeldung: "der Typ ' ' konnte nicht geladen werden \<type name> . Stellen Sie sicher, dass die Assembly, die diesen Typ enthält, den Projekt verweisen hinzugefügt wird. "

Visual Studio hat versucht, eine Methode für die Ereignis Behandlung zu verknüpfen, und mindestens einen Parametertypen für die Methode konnte nicht gefunden werden. Dies wird normalerweise durch einen fehlenden Verweis verursacht. Um diesen Fehler zu beheben, fügen Sie dem Projekt den Verweis mit dem Typ hinzu, und wiederholen Sie den Vorgang.

### <a name="could-not-locate-the-project-item-templates-for-inherited-components"></a>Die Projektelementvorlagen für geerbte Komponenten konnten nicht gefunden werden

Die Vorlagen für geerbte Formulare in Visual Studio sind nicht verfügbar. Wenn dieser Fehler angezeigt wird, melden Sie sich mit " [Problem melden](/visualstudio/ide/how-to-report-a-problem-with-visual-studio)" an.

### <a name="delegate-class-class-name-has-no-invoke-method-is-this-class-a-delegate"></a>Die Delegatklasse " \<class name> " hat keine Aufruf Methode. Ist diese Klasse ein Delegat?

Visual Studio hat versucht, einen Ereignishandler zu erstellen, aber es gibt ein Problem mit dem Ereignistyp. Dies kann vorkommen, wenn das Ereignis durch eine nicht CLS-kompatible Sprache erstellt wurde. Wenden Sie sich an den Komponentenhersteller.

### <a name="duplicate-declaration-of-member-member-name"></a>Doppelte Deklaration des Members " \<member name> "

Dieser Fehler tritt auf, weil eine Member-Variable zweimal deklariert wurde (z. b. werden zwei Steuerelemente `Button1` mit dem Namen im Code deklariert). Namen müssen über geerbte Formulare hinweg eindeutig sein. Außerdem dürfen sich Namen nur in der Groß-/Kleinschreibung unterscheiden

### <a name="error-reading-resources-from-the-resource-file-for-the-culture-culture-name"></a>Fehler beim Lesen der Ressourcen aus der Ressourcen Datei für die Kultur " \<culture name> ".

Dieser Fehler kann auftreten, wenn eine ungültige RESX-Datei im Projekt vorhanden ist.

Diesen Fehler können Sie wie folgt beheben:

1. Klicken Sie in Projektmappen-Explorer auf die Schaltfläche **alle Dateien anzeigen** , um die der Projekt Mappe zugeordneten RESX-Dateien anzuzeigen.
2. Laden Sie die RESX-Datei im XML-Editor, indem Sie mit der rechten Maustaste auf die RESX-Datei klicken und **Öffnen**auswählen.
3. Bearbeiten Sie die RESX-Datei manuell, um die Fehler zu beheben.

### <a name="error-reading-resources-from-the-resource-file-for-the-default-culture-culture-name"></a>Fehler beim Lesen der Ressourcen aus der Ressourcen Datei für die Standard Kultur " \<culture name> ".

Dieser Fehler kann auftreten, wenn im Projekt eine ungültige RESX-Datei für die Standard Kultur vorhanden ist.

Diesen Fehler können Sie wie folgt beheben:

1. Klicken Sie in Projektmappen-Explorer auf die Schaltfläche **alle Dateien anzeigen** , um die der Projekt Mappe zugeordneten RESX-Dateien anzuzeigen.
2. Laden Sie die RESX-Datei im XML-Editor, indem Sie mit der rechten Maustaste auf die RESX-Datei klicken und **Öffnen**auswählen.
3. Bearbeiten Sie die RESX-Datei manuell, um die Fehler zu beheben.

### <a name="failed-to-parse-method-method-name"></a>Die Methode "" konnte nicht analysiert werden. \<method name>

Fehlermeldung: "die Methode" "konnte nicht analysiert werden \<method name> . Der Parser hat den folgenden Fehler gemeldet: " \<error string> ". Überprüfen Sie die Aufgabenliste auf mögliche Fehler. "

Dies ist eine allgemeine Fehlermeldung für Probleme, die während der Verarbeitung auftreten. Diese Fehler sind häufig auf Syntax Fehler zurückzuführen. Informationen zu bestimmten Meldungen im Zusammenhang mit dem Fehler finden Sie in der Aufgabenliste.

### <a name="invalid-component-name-component-name"></a>Ungültiger Komponenten Name: " \<component name> "

Sie haben versucht, eine Komponente in einen ungültigen Wert für diese Sprache umzubenennen. Benennen Sie die Komponente so, dass Sie den Benennungs Regeln für diese Sprache entspricht, um diesen Fehler zu beheben.

### <a name="the-type-class-name-is-made-of-several-partial-classes-in-the-same-file"></a>Der Typ " \<class name> " besteht aus mehreren partiellen Klassen in derselben Datei.

Wenn Sie eine Klasse in mehreren Dateien mit dem [partiellen](../../../csharp/language-reference/keywords/partial-type.md) Schlüsselwort definieren, können Sie nur eine partielle Definition in jeder Datei verwenden.

Um diesen Fehler zu beheben, entfernen Sie bis auf eine der partiellen Definitionen der Klasse aus der Datei.

### <a name="the-assembly-assembly-name-could-not-be-found"></a>Die Assembly " \<assembly name> " konnte nicht gefunden werden.

Fehlermeldung: "die Assembly ' ' wurde \<assembly name> nicht gefunden. Stellen Sie sicher, dass auf die Assembly verwiesen wird. Wenn die Assembly Teil des aktuellen Entwicklungsprojekts ist, stellen Sie sicher, dass das Projekt erstellt wurde. "

Dieser Fehler ähnelt dem "der Typ ' \<type name> ' wurde nicht gefunden", aber dieser Fehler tritt in der Regel aufgrund eines metadatenattributs auf. Überprüfen Sie, ob auf alle von Attributen verwendeten Assemblys verwiesen wird, um diesen Fehler zu beheben.

### <a name="the-assembly-name-assembly-name-is-invalid"></a>Der Assemblyname " \<assembly name> " ist ungültig.

Eine Komponente hat eine bestimmte Assembly angefordert, aber der von der Komponente angegebene Name ist kein gültiger AssemblyName. Wenden Sie sich an den Komponentenhersteller.

### <a name="the-base-class-class-name-cannot-be-designed"></a>Die Basisklasse " \<class name> " kann nicht entworfen werden.

Die Klasse wurde von Visual Studio geladen, aber die Klasse kann nicht entworfen werden, da der Implementierer der Klasse keinen Designer bereitgestellt hat. Wenn die Klasse einen Designer unterstützt, stellen Sie sicher, dass keine Probleme auftreten, die Probleme bei der Anzeige in einem Designer verursachen, z. b. Compilerfehler. Stellen Sie außerdem sicher, dass alle Verweise auf die Klasse korrekt sind und alle Klassennamen richtig geschrieben sind. Wenn die Klasse nicht Entwurfs fähig ist, bearbeiten Sie Sie in der Code Ansicht.

### <a name="the-base-class-class-name-could-not-be-loaded"></a>Die Basisklasse ' \<class name> ' konnte nicht geladen werden.

Auf die-Klasse wird im Projekt nicht verwiesen, sodass Sie von Visual Studio nicht geladen werden kann. Fügen Sie einen Verweis auf die-Klasse im Projekt hinzu, und schließen Sie das Windows Forms-Designer Fenster, und öffnen Sie es erneut, um diesen Fehler zu beheben.

### <a name="the-class-class-name-cannot-be-designed-in-this-version-of-visual-studio"></a>Die-Klasse \<class name> kann in dieser Version von Visual Studio nicht entworfen werden.

Der Designer für dieses Steuerelement oder diese Komponente unterstützt nicht die gleichen Typen wie Visual Studio. Wenden Sie sich an den Komponentenhersteller.

### <a name="the-class-name-is-not-a-valid-identifier-for-this-language"></a>Der Klassenname ist kein gültiger Bezeichner für diese Sprache

Der Quell Code, der vom Benutzer erstellt wird, hat einen Klassennamen, der für die verwendete Sprache ungültig ist. Benennen Sie die Klasse so, dass Sie den Sprachanforderungen entspricht, um diesen Fehler zu beheben.

### <a name="the-component-cannot-be-added-because-it-contains-a-circular-reference-to-reference-name"></a>Die Komponente kann nicht hinzugefügt werden, da Sie einen Zirkel Verweis auf "" enthält. \<reference name>

Ein Steuerelement oder eine Komponente kann nicht selbst hinzugefügt werden. Eine weitere Situation, in der dies auftreten kann, ist, wenn in der InitializeComponent-Methode eines Formulars (z. b. Form1) Code vorhanden ist, der eine andere Instanz von Form1 erstellt.

### <a name="the-designer-cannot-be-modified-at-this-time"></a>Der Designer kann derzeit nicht geändert werden

Dieser Fehler tritt auf, wenn die Datei im Editor als schreibgeschützt gekennzeichnet ist. Stellen Sie sicher, dass die Datei nicht als schreibgeschützt gekennzeichnet ist und die Anwendung nicht ausgeführt wird.

### <a name="the-designer-could-not-be-shown-for-this-file-because-none-of-the-classes-within-it-can-be-designed"></a>Der Designer konnte für diese Datei nicht angezeigt werden, da keine der enthaltenen Klassen entworfen werden kann.

Dieser Fehler tritt auf, wenn Visual Studio keine Basisklasse finden kann, die die Designer Anforderungen erfüllt. Formulare und Steuerelemente müssen von einer Basisklasse abgeleitet werden, die Designer unterstützt. Wenn Sie von einem geerbten Formular oder Steuerelement ableiten, stellen Sie sicher, dass das Projekt erstellt wurde.

### <a name="the-designer-for-base-class-class-name-is-not-installed"></a>Der Designer für die Basisklasse " \<class name> " ist nicht installiert.

Visual Studio konnte den Designer für die Klasse nicht laden. Wenn dieser Fehler angezeigt wird, melden Sie sich mit " [Problem melden](/visualstudio/ide/how-to-report-a-problem-with-visual-studio)" an.

### <a name="the-designer-must-create-an-instance-of-type-type-name-but-it-cant-because-the-type-is-declared-as-abstract"></a>Der Designer muss eine Instanz vom Typ " \<type name> " erstellen, dies ist jedoch nicht möglich, weil der Typ als abstrakt deklariert ist.

Dieser Fehler ist aufgetreten, da die Basisklasse des Objekts, das an den Designer übermittelt wird, [abstrakt](../../../csharp/language-reference/keywords/abstract.md)ist, was nicht zulässig ist.

### <a name="the-file-could-not-be-loaded-in-the-designer"></a>Die Datei konnte nicht in den Designer geladen werden

Die Basisklasse dieser Datei unterstützt keine Designer. Um dieses Problem zu umgehen, verwenden Sie die Code Ansicht, um an der Datei zu arbeiten. Klicken Sie mit der rechten Maustaste auf die Datei in Projektmappen-Explorer und wählen Sie **Code anzeigen**aus.

### <a name="the-language-for-this-file-does-not-support-the-necessary-code-parsing-and-generation-services"></a>Die Sprache für diese Datei unterstützt die erforderlichen Codeverarbeitungs- und die Generierungsdienste nicht.

Fehlermeldung: "die Sprache für diese Datei unterstützt nicht die erforderlichen Code-und Generierungs Dienste. Stellen Sie sicher, dass die Datei, die Sie öffnen, Mitglied eines Projekts ist, und versuchen Sie dann erneut, die Datei zu öffnen. "

Dieser Fehler ist wahrscheinlich auf das Öffnen einer Datei zurückzuführen, die sich in einem Projekt befindet, das keine Designer unterstützt.

### <a name="the-language-parser-class-class-name-is-not-implemented-properly"></a>Die sprach Parser-Klasse " \<class name> " ist nicht ordnungsgemäß implementiert.

Fehlermeldung: "die sprach Parser-Klasse ' \<class name> ' ist nicht ordnungsgemäß implementiert. Wenden Sie sich für ein aktualisiertes Parsermodul an den Hersteller. "

Die verwendete Sprache hat eine Designer Klasse registriert, die nicht von der richtigen Basisklasse abgeleitet ist. Wenden Sie sich an den Hersteller der von Ihnen verwendeten Sprache.

### <a name="the-name-name-is-already-used-by-another-object"></a>Der Name " \<name> " wird bereits von einem anderen Objekt verwendet.

Dies ist ein interner Fehler im Visual Studio-Serialisierungsprogramm. Wenn dieser Fehler angezeigt wird, melden Sie sich mit " [Problem melden](/visualstudio/ide/how-to-report-a-problem-with-visual-studio)" an.

### <a name="the-object-object-name-does-not-implement-the-icomponent-interface"></a>Das-Objekt \<object name> implementiert die IComponent-Schnittstelle nicht.

Visual Studio hat versucht, eine Komponente zu erstellen, aber das erstellte Objekt implementiert die- <xref:System.ComponentModel.IComponent> Schnittstelle nicht. Wenden Sie sich für eine Korrektur an den Hersteller der Komponente.

### <a name="the-object-object-name-returned-null-for-the-property-property-name-but-this-is-not-allowed"></a>Das-Objekt ' ' \<object name> gab NULL für die-Eigenschaft zurück, \<property name> Dies ist jedoch nicht zulässig.

Einige .net-Eigenschaften sollten immer ein-Objekt zurückgeben. Beispielsweise sollte die **Controls** -Auflistung eines Formulars immer ein Objekt zurückgeben, auch wenn keine Steuerelemente darin vorhanden sind.

Stellen Sie sicher, dass die im Fehler angegebene Eigenschaft nicht NULL ist, um diesen Fehler zu beheben.

### <a name="the-serialization-data-object-is-not-of-the-proper-type"></a>Das Serialisierungsdatenobjekt hat den falschen Typ

Ein vom Serialisierungsprogramm angebotenes Datenobjekt ist keine Instanz eines Typs, der mit dem aktuellen Serialisierungsprogramm übereinstimmt, das verwendet wird. Wenden Sie sich an den Komponentenhersteller.

### <a name="the-service-service-name-is-required-but-could-not-be-located"></a>Der Dienst " \<service name> " ist erforderlich, konnte aber nicht gefunden werden.

Fehlermeldung: "der Dienst ' \<service name> ' ist erforderlich, konnte jedoch nicht gefunden werden. Möglicherweise liegt ein Problem mit Ihrer Visual Studio-Installation vor. "

Ein von Visual Studio benötigtes Dienst ist nicht verfügbar. Wenn Sie ein Projekt laden möchten, das den Designer nicht unterstützt, verwenden Sie den Code-Editor, um die erforderlichen Änderungen vorzunehmen. Wenn dieser Fehler angezeigt wird, melden Sie sich mit " [Problem melden](/visualstudio/ide/how-to-report-a-problem-with-visual-studio)" an.

### <a name="the-service-instance-must-derive-from-or-implement-interface-name"></a>Die Dienst Instanz muss von abgeleitet oder implementiert werden. \<interface name>

Dieser Fehler zeigt an, dass eine Komponente oder ein Komponenten-Designer die **AddService** -Methode aufgerufen hat, die eine Schnittstelle und ein Objekt erfordert, aber das angegebene Objekt implementiert nicht die angegebene Schnittstelle. Wenden Sie sich an den Komponentenhersteller.

### <a name="the-text-in-the-code-window-could-not-be-modified"></a>Der Text im Code-Editor konnte nicht geändert werden

Fehlermeldung: "der Text im Code Fenster konnte nicht geändert werden. Überprüfen Sie, ob die Datei nicht schreibgeschützt ist und dass ausreichend Speicherplatz vorhanden ist. "

Dieser Fehler tritt auf, wenn Visual Studio eine Datei aufgrund von Speicherplatz oder Arbeitsspeicher Problemen nicht bearbeiten kann oder wenn die Datei als schreibgeschützt gekennzeichnet ist.

### <a name="the-toolbox-enumerator-object-only-supports-retrieving-one-item-at-a-time"></a>Das Toolbox-Enumerationsobjekt unterstützt nur das Abfragen von einem Element gleichzeitig

Wenn dieser Fehler angezeigt wird, melden Sie sich, wenn dieser Fehler angezeigt wird, mit " [Problem melden](/visualstudio/ide/how-to-report-a-problem-with-visual-studio)" an.

### <a name="the-toolbox-item-for-component-name-could-not-be-retrieved-from-the-toolbox"></a>Das Toolbox Element für " \<component name> " konnte nicht aus der Toolbox abgerufen werden.

Fehlermeldung: "das Toolbox Element für ' \<component name> ' konnte nicht aus der Toolbox abgerufen werden. Stellen Sie sicher, dass die Assembly, die das Toolbox Element enthält, ordnungsgemäß installiert ist. Das Toolbox Element hat den folgenden Fehler ausgelöst: \<error string> . "

Die betreffende Komponente hat eine Ausnahme ausgelöst, als Visual Studio darauf zugegriffen hat. Wenden Sie sich an den Komponentenhersteller.

### <a name="the-toolbox-item-for-toolbox-item-name-could-not-be-retrieved-from-the-toolbox"></a>Das Toolbox Element für " \<Toolbox item name> " konnte nicht aus der Toolbox abgerufen werden.

Fehlermeldung: "das Toolbox Element für ' \<Toolbox item name> ' konnte nicht aus der Toolbox abgerufen werden. Entfernen Sie das Element aus der Toolbox, und fügen Sie es wieder hinzu. "

Dieser Fehler tritt auf, wenn die Daten innerhalb des Toolbox Elements beschädigt werden oder sich die Version der Komponente geändert hat. Entfernen Sie das Element aus der Toolbox, und fügen Sie es wieder hinzu.

### <a name="the-type-type-name-could-not-be-found"></a>Der Typ " \<type name> " konnte nicht gefunden werden.

Fehlermeldung: "der Typ" "wurde \<type name> nicht gefunden. Stellen Sie sicher, dass auf die Assembly mit dem Typ verwiesen wird. Wenn die Assembly Teil des aktuellen Entwicklungsprojekts ist, stellen Sie sicher, dass das Projekt erstellt wurde. "

Beim Laden des Designers konnte von Visual Studio kein Typ gefunden werden. Stellen Sie sicher, dass auf die Assembly mit dem Typ verwiesen wird. Wenn die Assembly Teil des aktuellen Entwicklungsprojekts ist, stellen Sie sicher, dass das Projekt erstellt wurde.

### <a name="the-type-resolution-service-may-only-be-called-from-the-main-application-thread"></a>Der Typauflösungsdienst kann nur vom Hauptanwendungsthread aufgerufen werden

Visual Studio hat versucht, auf die erforderlichen Ressourcen aus dem falschen Thread zuzugreifen. Dieser Fehler wird angezeigt, wenn der Code, der zum Erstellen des Designers verwendet wurde, den Typauflösungs Dienst von einem anderen Thread als dem Hauptanwendungs Thread aufgerufen hat. Um diesen Fehler zu beheben, müssen Sie den Dienst aus dem richtigen Thread abrufen oder den Hersteller der Komponente kontaktieren.

### <a name="the-variable-variable-name-is-either-undeclared-or-was-never-assigned"></a>Die Variable " \<variable name> " ist entweder nicht deklariert oder wurde nie zugewiesen.

Der Quellcode enthält einen Verweis auf eine Variable, z. b. **Button1**, die nicht deklariert oder zugewiesen ist. Wenn die Variable nicht zugewiesen wurde, wird diese Meldung als Warnung, nicht als Fehler angezeigt.

### <a name="there-is-already-a-command-handler-for-the-menu-command-menu-command-name"></a>Es ist bereits ein Befehls Handler für den Menübefehl " \<menu command name> " vorhanden.

Dieser Fehler tritt auf, wenn ein Drittanbieter-Designer einen Befehl hinzufügt, der bereits über einen Handler für die Befehls Tabelle verfügt. Wenden Sie sich an den Komponentenhersteller.

### <a name="there-is-already-a-component-named-component-name"></a>Es ist bereits eine Komponente mit dem Namen "" vorhanden. \<component name>

Fehlermeldung: "Es ist bereits eine Komponente mit dem Namen ' \<component name> ' vorhanden. Komponenten müssen eindeutige Namen aufweisen, und bei Namen darf die Groß-/Kleinschreibung nicht beachtet werden. Ein Name kann auch nicht mit dem Namen einer Komponente in einer geerbten Klasse in Konflikt stehen. "

Diese Fehlermeldung wird angezeigt, wenn der Name einer Komponente im Eigenschaftenfenster geändert wurde. Stellen Sie sicher, dass alle Komponentennamen eindeutig sind, nicht zwischen Groß-und Kleinschreibung unterliegen und nicht mit den Namen von Komponenten in den geerbten Klassen in Konflikt stehen, um diesen Fehler zu beheben.

### <a name="there-is-already-a-toolbox-item-creator-registered-for-the-format-format-name"></a>Es ist bereits ein Toolbox Element-Ersteller für das Format "" registriert. \<format name>

Eine Drittanbieter Komponente hat einen Rückruf an ein Element auf einer Toolbox Registerkarte vorgenommen, aber das Element enthielt bereits einen Rückruf. Wenden Sie sich an den Komponentenhersteller.

### <a name="this-language-engine-does-not-support-a-codemodel-with-which-to-load-a-designer"></a>Ein Codemodell, mit dem ein Designer geladen wird, wird von dieser Sprach-Engine nicht unterstützt

Diese Meldung ähnelt der Meldung "die Sprache für diese Datei unterstützt nicht die erforderliche Code-und Generierungs Dienste", aber diese Meldung enthält ein internes Registrierungsproblem. Wenn dieser Fehler angezeigt wird, melden Sie sich, wenn dieser Fehler angezeigt wird, mit " [Problem melden](/visualstudio/ide/how-to-report-a-problem-with-visual-studio)" an.

### <a name="type-type-name-does-not-have-a-constructor-with-parameters-of-types-parameter-type-names"></a>Der Typ "" \<type name\> weist keinen Konstruktor mit Parametern vom Typ " \<parameter type names> " auf.

Visual Studio konnte keinen [Konstruktor](../../../csharp/programming-guide/classes-and-structs/constructors.md) finden, der übereinstimmende Parameter enthielt. Dies kann das Ergebnis sein, wenn ein Konstruktor mit anderen Typen als den erforderlichen Typen bereitgestellt wird. Ein **punktkonstruktor** kann z. b. zwei ganze Zahlen annehmen. Wenn Sie Gleit Komma Zahlen angegeben haben, wird dieser Fehler ausgelöst.

Um diesen Fehler zu beheben, verwenden Sie einen anderen Konstruktor, oder wandeln Sie die Parametertypen explizit um, damit Sie mit den vom Konstruktor bereitgestellten Typen identisch sind.

### <a name="unable-to-add-reference-reference-name-to-the-current-application"></a>Der Verweis "" kann \<reference name> der aktuellen Anwendung nicht hinzugefügt werden.

Fehlermeldung: "der Verweis ' ' konnte \<reference name> der aktuellen Anwendung nicht hinzugefügt werden. Überprüfen Sie, ob nicht bereits auf eine andere Version von ' \<reference name> ' verwiesen wird.

Visual Studio kann keinen Verweis hinzufügen. Um diesen Fehler zu beheben, überprüfen Sie, ob nicht bereits auf eine andere Version des Verweises verwiesen wird.

### <a name="unable-to-check-out-the-current-file"></a>Die aktuelle Datei konnte nicht ausgecheckt werden

Fehlermeldung: "die aktuelle Datei kann nicht ausgecheckt werden. Möglicherweise ist die Datei gesperrt, oder Sie müssen die Datei möglicherweise manuell auschecken. "

Dieser Fehler tritt auf, wenn Sie eine aktuell eingecheckte Datei in die Quell Code Verwaltung ändern. In der Regel zeigt Visual Studio das Dialogfeld zum Auschecken von Dateien an, sodass der Benutzer die Datei Auschecken kann. Dieses Mal wurde die Datei nicht ausgecheckt, möglicherweise aufgrund eines Mergekonflikts beim Auschecken. Stellen Sie sicher, dass die Datei nicht gesperrt ist, und versuchen Sie dann, die Datei manuell auszuchecken, um diesen Fehler zu beheben.

### <a name="unable-to-find-page-named-options-dialog-box-tab-name"></a>Die Seite mit dem Namen "" wurde nicht gefunden. \<Options dialog box tab name>

Dieser Fehler tritt auf, wenn ein Komponenten-Designer den Zugriff auf eine Seite über das Dialogfeld Optionen unter Verwendung eines nicht vorhandenen namens anfordert. Wenden Sie sich an den Komponentenhersteller.

### <a name="unable-to-find-property-property-name-on-page-options-dialog-box-tab-name"></a>Die Eigenschaft "" wurde \<property name> auf der Seite " \<Options dialog box tab name> " nicht gefunden.

Dieser Fehler tritt auf, wenn ein Komponenten-Designer den Zugriff auf einen bestimmten Wert auf einer Seite im Dialogfeld Optionen anfordert, dieser Wert jedoch nicht vorhanden ist. Wenden Sie sich an den Komponentenhersteller.

### <a name="visual-studio-cannot-open-a-designer-for-the-file-because-the-class-within-it-does-not-inherit-from-a-class-that-can-be-visually-designed"></a>Visual Studio kann für die Datei keine Designer öffnen, da die Klasse innerhalb der Datei nicht von einer Klasse erbt, die mit einem Designer bearbeitet werden kann

Die Klasse wurde von Visual Studio geladen, aber der Designer für diese Klasse konnte nicht geladen werden. Visual Studio erfordert, dass Designer die erste Klasse in einer Datei verwenden. Verschieben Sie den Klassen Code so, dass er die erste Klasse in der Datei ist, und laden Sie den Designer dann erneut, um diesen Fehler zu beheben.

### <a name="visual-studio-cannot-save-or-load-instances-of-the-type-type-name"></a>Visual Studio kann keine Instanzen vom Typ "" Speichern oder laden. \<type name>

Dies ist ein Problem mit einer Drittanbieter Komponente. Wenden Sie sich an den Komponentenhersteller.

### <a name="visual-studio-is-unable-to-open-document-name-in-design-view"></a>Visual Studio kann " \<document name> " in Designansicht nicht öffnen.

Fehlermeldung: "Visual Studio kann '" \<document name> in Designansicht nicht öffnen. Für den Dateityp ist kein Parser installiert. "

Dieser Fehler zeigt an, dass die Sprache des Projekts keinen Designer unterstützt und beim Versuch, eine Datei im Dialogfeld Datei öffnen oder in Projektmappen-Explorer zu öffnen. Bearbeiten Sie die Datei stattdessen in der Code Ansicht.

### <a name="visual-studio-was-unable-to-find-a-designer-for-classes-of-type-type-name"></a>Visual Studio konnte keinen Designer für Klassen vom Typ " \<type name> " finden

Die Klasse wurde von Visual Studio geladen, aber die Klasse kann nicht entworfen werden. Bearbeiten Sie stattdessen die-Klasse in der Code Ansicht, indem Sie mit der rechten Maustaste auf die Klasse klicken und **Code anzeigen**auswählen.

## <a name="see-also"></a>Weitere Informationen

- [Entwickeln von Windows Forms-Steuerelementen mithilfe des Designers](developing-windows-forms-controls-at-design-time.md)
- [Windows Forms-Designer Forum](https://social.msdn.microsoft.com/Forums/windows/home?forum=winformsdesigner)

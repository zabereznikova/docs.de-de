---
title: "Troubleshooting Interoperability (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "interop, deploying assemblies"
  - "assemblies [Visual Basic]"
  - "interop, installing assemblies that share components"
  - "COM objects, troubleshooting"
  - "interop, sharing components"
  - "troubleshooting interoperability"
  - "interoperability, troubleshooting"
  - "COM interop, troubleshooting"
  - "assemblies [Visual Basic], deploying"
  - "troubleshooting Visual Basic, interoperability"
  - "interop assemblies"
  - "interoperability, sharing components"
  - "shared components, using with assemblies"
ms.assetid: b324cc1e-b03c-4f39-aea6-6a6d5bfd0e37
caps.latest.revision: 21
caps.handback.revision: 21
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Troubleshooting Interoperability (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Bei der gemeinsamen Verwendung von COM und verwaltetem Code von [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] sind möglicherweise die folgenden allgemeinen Themen von Belang.  
  
##  <a name="vbconinteroperabilitymarshalinganchor1"></a> Interop\-Marshalling  
 Gelegentlich müssen Sie Datentypen verwenden, die nicht Bestandteil von [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] sind.  Interop\-Assemblys bewältigen den Großteil der für COM\-Objekte erforderlichen Aufgaben. Möglicherweise müssen Sie jedoch die Datentypen steuern, die beim Verfügbarmachen verwalteter Objekte für COM verwendet werden.  Strukturen in Klassenbibliotheken müssen z. B. den nicht verwalteten Typ `BStr` für Zeichenfolgen angeben, die an mit Visual Basic 6.0 und älteren Versionen erstellte COM\-Objekte gesendet werden.  In diesen Fällen können Sie das <xref:System.Runtime.InteropServices.MarshalAsAttribute>\-Attribut verwenden, damit verwaltete Typen als nicht verwaltete Typen verfügbar gemacht werden.  
  
##  <a name="vbconinteroperabilitymarshalinganchor2"></a> Exportieren von Zeichenfolgen fester Länge in nicht verwalteten Code  
 Bei Visual Basic 6.0 und älteren Versionen werden Zeichenfolgen als Bytefolgen ohne abschließendes NULL\-Zeichen in COM\-Objekte exportiert.  Aus Gründen der Kompatibilität mit anderen Sprachen fügt [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong-md.md)] beim Exportieren von Zeichenfolgen ein abschließendes Zeichen ein.  Um diese Inkompatibilität zu beheben, können Sie Zeichenfolgen ohne abschließendes Zeichen als `Byte` oder `Char` exportieren.  
  
##  <a name="vbconinteroperabilitymarshalinganchor3"></a> Exportieren von Vererbungshierarchien  
 Hierarchien verwalteter Klassen gehen beim Verfügbar machen als COM\-Objekte verloren.  Wenn Sie z. B. eine Basisklasse mit einem Member definieren und diese an eine abgeleitete Klasse vererben, die als COM\-Objekt offen gelegt wird, können Clients, die diese abgeleitete Klasse als COM\-Objekt verwenden, die geerbten Member nicht verwenden.  Auf Basisklassenmember kann von COM\-Objekten nur als Instanzen einer Basisklasse zugegriffen werden, und dies auch nur dann, wenn die Basisklasse ebenfalls als COM\-Objekt erstellt wurde.  
  
## Überladene Methoden  
 Sie können mit [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] zwar überladene Methoden erstellen, diese werden jedoch von COM nicht unterstützt.  Wenn eine Klasse, die überladene Methoden enthält, als COM\-Objekt verfügbar gemacht wird, werden für die überladenen Methoden neue Methodennamen generiert.  
  
 Angenommen, Sie verfügen über eine Klasse mit zwei Überladungen der `Synch`\-Methode.  Wenn die Klasse als COM\-Objekt verfügbar gemacht wird, könnten die neu generierten Methodennamen `Synch` und `Synch_2` lauten.  
  
 Die Umbenennung kann für Benutzer des COM\-Objekts zu zwei Problemen führen.  
  
1.  Möglicherweise erwarten die Clients die generierten Methodennamen nicht.  
  
2.  Die generierten Methodennamen in der als COM\-Objekt verfügbar gemachten Klasse ändern sich möglicherweise, wenn der Klasse oder ihrer Basisklasse neue Überladungen hinzugefügt werden.  Dies kann Versionsprobleme verursachen.  
  
 Zum Lösen beider Probleme müssen Sie bei der Entwicklung von Objekten, die als COM\-Objekte verfügbar gemacht werden, jeder Methode einen eindeutigen Namen zuweisen, anstatt Überladungen zu verwenden.  
  
##  <a name="vbconinteroperabilitymarshalinganchor4"></a> Verwenden von COM\-Objekten über Interop\-Assemblys  
 Interop\-Assemblys lassen sich nahezu wie Ersetzungen der von ihnen dargestellten COM\-Objekte durch verwalteten Code verwenden.  Da sie aber Wrapper und keine eigentlichen COM\-Objekte sind, weist die Verwendung von Interop\-Assemblys und Standardassemblys einige Unterschiede auf.  Diese betreffen das Verfügbar machen von Klassen ebenso wie Datentypen für Parameter und Rückgabewerte.  
  
##  <a name="vbconinteroperabilitymarshalinganchor5"></a> Klassen, die als Schnittstellen und als Klassen offen gelegt werden  
 Im Gegensatz zu Klassen in Standardassemblys werden COM\-Klassen in Interop\-Assemblys sowohl als Schnittstelle als auch als Klasse offen gelegt, die die COM\-Klasse darstellt.  Der Name der Schnittstelle ist mit dem der COM\-Klasse identisch.  Der Name der Interop\-Klasse stimmt mit dem Namen der ursprünglichen COM\-Klasse überein, allerdings wird "Class" angefügt.  Angenommen, ein Projekt enthält einen Verweis auf eine Interop\-Assembly für ein COM\-Objekt.  Wenn die COM\-Klasse den Namen `MyComClass` hat, wird in IntelliSense und im Objektkatalog die Schnittstelle `MyComClass` und die Klasse `MyComClassClass` angezeigt.  
  
##  <a name="vbconinteroperabilitymarshalinganchor6"></a> Erstellen von Instanzen einer .NET Framework\-Klasse  
 Im Allgemeinen erstellen Sie eine Instanz einer [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)]\-Klasse mithilfe der `New`\-Anweisung und einem Klassennamen.  Sie können die `New`\-Anweisung nur dann mit einer Schnittstelle verwenden, wenn Sie über eine durch eine Interop\-Assembly dargestellte COM\-Klasse verfügen.  Wenn Sie die COM\-Klasse nicht mit einer `Inherits`\-Anweisung verwenden, können Sie die Schnittstelle wie eine Klasse verwenden.  Der folgende Code demonstriert die Erstellung eines `Command`\-Objekts in einem Projekt, das über einen Verweis auf das COM\-Objekt der Microsoft ActiveX Data Objects 2.8\-Bibliothek verfügt:  
  
 [!code-vb[VbVbalrInterop#20](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/vbvbalrinterop/Class1.vb#20)]  
  
 Bei Verwendung der COM\-Klasse als Basis für eine abgeleitete Klasse müssen Sie jedoch die Interop\-Klasse verwenden, die die COM\-Klasse darstellt, wie im folgenden Code gezeigt:  
  
 [!code-vb[VbVbalrInterop#21](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/vbvbalrinterop/Class1.vb#21)]  
  
> [!NOTE]
>  Interop\-Assemblys implementieren implizit Schnittstellen, die COM\-Klassen darstellen.  Implementieren Sie diese Schnittstellen nicht mit der `Implements`\-Anweisung. Dies löst einen Fehler aus.  
  
##  <a name="vbconinteroperabilitymarshalinganchor7"></a> Datentypen für Parameter und Rückgabewerte  
 Im Gegensatz zu Membern von Standardassemblys können Member von Interop\-Assemblys über Datentypen verfügen, die nicht mit denen in der ursprünglichen Deklaration des Objekts übereinstimmen.  Interop\-Assemblys konvertieren COM\-Typen implizit in mit Common Language Runtime kompatible Typen. Sie sollten jedoch die auf beiden Seiten verwendeten Datentypen überprüfen, um Laufzeitfehler zu vermeiden.  Bei COM\-Objekten, die in Visual Basic 6.0 und älteren Versionen erstellt wurden, gehen z. B. Werte vom Typ `Integer` vom äquivalenten [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)]\-Typ \(`Short`\) aus.  Verwenden Sie nach Möglichkeit den Objektkatalog, um die Merkmale importierter Member vor der Verwendung zu überprüfen.  
  
##  <a name="vbconinteroperabilitymarshalinganchor8"></a> COM‑Methoden auf Modulebene  
 Die meisten COM‑Objekte werden verwendet, indem mit dem `New`\-Schlüsselwort eine Instanz einer COM‑Klasse erstellt wird und dann die Methoden des Objekts aufgerufen werden.  Eine Ausnahme dieser Regel betrifft COM\-Objekte, die `AppObj`\- oder `GlobalMultiUse`\-COM\-Klassen enthalten.  Solche Klassen entsprechen den Methoden auf Modulebene in [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong-md.md)]\-Klassen.  Visual Basic 6.0 und frühere Versionen erstellen Instanzen solcher Objekte implizit, wenn Sie das erste Mal eine ihrer Methoden aufrufen.  Beispielsweise können Sie in Visual Basic 6.0 einen Verweis auf die Microsoft DAO 3.6 Object\-Bibliothek hinzufügen und die `DBEngine`\-Methode aufrufen, ohne zuerst eine Instanz erstellen zu müssen:  
  
```  
Dim db As DAO.Database  
' Open the database.  
Set db = DBEngine.OpenDatabase("C:\nwind.mdb")  
' Use the database object.  
```  
  
 In [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong-md.md)] müssen immer zuerst Instanzen von COM\-Objekten erstellt werden, bevor Sie deren Methoden verwenden können.  Um diese Methoden in [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong-md.md)] zu verwenden, deklarieren Sie eine Variable der gewünschten Klasse und weisen das Objekt mit dem new\-Schlüsselwort der Objektvariable zu.  Das `Shared`\-Schlüsselwort können Sie verwenden, wenn Sie sicherstellen möchten, dass nur eine Instanz der Klasse erstellt wird.  
  
 [!code-vb[VbVbalrInterop#23](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/vbvbalrinterop/Class1.vb#23)]  
  
##  <a name="vbconinteroperabilitymarshalinganchor9"></a> Nicht behandelte Fehler in Ereignishandlern  
 Ein häufig vorkommendes Interop\-Problem hängt mit Fehlern in Ereignishandlern zusammen, die durch COM‑Objekte ausgelöste Ereignisse behandeln.  Solche Fehler werden ignoriert, es sei denn, Sie führen mit einer `On Error`\-Anweisung oder einer `Try...Catch...Finally`\-Anweisung explizit eine Fehlerprüfung durch.  Das folgende Beispiel stammt aus einem [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong-md.md)]\-Projekt mit einem Verweis auf das COM\-Objekt der Microsoft ActiveX Data Objects 2.8\-Bibliothek.  
  
 [!code-vb[VbVbalrInterop#24](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/vbvbalrinterop/Class1.vb#24)]  
  
 In diesem Beispiel wird ein Fehler wie erwartet ausgelöst.  Wenn Sie den gleichen Beispielcode jedoch ohne den `Try...Catch...Finally`\-Block ausführen, wird der Fehler ignoriert, so als ob Sie die `OnError Resume Next`\-Anweisung verwendet hätten.  Ohne die Fehlerbehandlung schlägt die Division durch Null ohne weitere Meldung fehl.  Da diese Fehler zu keiner Zeit unbehandelte Ausnahmefehler auslösen, müssen Sie in Ereignishandlern für Ereignisse aus COM\-Objekten eine Form der Ausnahmebehandlung anwenden.  
  
### Untersuchen von COM‑Interop\-Fehlern  
 Ohne Fehlerbehandlung lösen Interop\-Aufrufe häufig Fehler aus, die nur wenig Hintergrundinformationen enthalten.  Verwenden Sie, wenn möglich, eine strukturierte Fehlerbehandlung, um mehr Informationen über die Probleme bereitzustellen, die eventuell auftreten.  Dies kann beim Debuggen von Anwendungen besonders hilfreich sein.  Beispiele:  
  
 [!code-vb[VbVbalrInterop#25](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/vbvbalrinterop/Class1.vb#25)]  
  
 Sie können Informationen wie die Fehlerbeschreibung, HRESULT, und den Ursprung von COM\-Fehlern abrufen, indem Sie den Inhalt des Ausnahmeobjekts untersuchen.  
  
##  <a name="vbconinteroperabilitymarshalinganchor10"></a> Probleme mit ActiveX\-Steuerelementen  
 Die meisten ActiveX\-Steuerelemente, die in Visual Basic 6.0 funktionieren, können auch in [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong-md.md)] problemlos verwendet werden.  Die wichtigste Ausnahme hierzu stellen Containersteuerelemente dar, oder Steuerelemente, die andere Steuerelemente sichtbar enthalten.  Einige Beispiele für ältere Steuerelemente, die in [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs-md.md)] nicht ordnungsgemäß ausgeführt werden:  
  
-   Microsoft Forms 2.0 Frame\-Steuerelement  
  
-   Auf\-Ab\-Steuerelement, auch Drehfeld\-Steuerelement genannt  
  
-   Sheridan\-Registersteuerelement  
  
 Für Probleme mit nicht unterstützten ActiveX\-Steuerelementen gibt es nur wenige Problemumgehungen.  Sie können vorhandene Steuerelemente in [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs-md.md)] migrieren, wenn Sie im Besitz des ursprünglichen Quellcodes sind.  Andernfalls können Sie bei Softwareanbietern nach aktualisierten .NET\-kompatiblen Versionen von Steuerelementen fragen, mit denen Sie nicht unterstützte ActiveX\-Steuerelemente ersetzen können.  
  
##  <a name="vbconinteroperabilitymarshalinganchor11"></a> Übergabe der ReadOnly\-Eigenschaften von Steuerelementen als ByRef\-Parameter  
 [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong-md.md)] löst unter Umständen COM\-Fehler \(z. B. "Error 0x800A017F CTL\_E\_SETNOTSUPPORTED"\) aus, wenn `ReadOnly`\-Eigenschaften älterer ActiveX\-Steuerelemente als `ByRef`\-Parameter an andere Prozeduren übergeben werden.  Ähnliche Prozeduraufrufe in Visual Basic 6.0 lösen keinen Fehler aus, und die Parameter werden behandelt, als ob Sie sie nach Wert übergeben würden.  Mit der in [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong-md.md)] angezeigten Fehlermeldung meldet das COM\-Objekt, dass Sie versuchen eine Eigenschaft ohne `Set`\-Eigenschaftenprozedur zu ändern.  
  
 Wenn Sie Zugriff auf die aufzurufende Prozedur haben, können Sie diesen Fehler verhindern, indem Sie mit dem `ByVal`\-Schlüsselwort Parameter deklarieren, die `ReadOnly`\-Eigenschaften akzeptieren.  Beispiele:  
  
 [!code-vb[VbVbalrInterop#26](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/vbvbalrinterop/Class1.vb#26)]  
  
 Wenn Sie keinen Zugriff auf den Quellcode für die aufzurufende Prozedur haben, können Sie die Übergabe der Eigenschaft nach Wert erzwingen, indem Sie ein zusätzliches Paar eckige Klammern um die aufrufende Prozedur herum einfügen.  So können Sie z. B. in einem Projekt mit einem Verweis auf das COM\-Objekt der Microsoft ActiveX Data Objects 2.8\-Bibliothek Folgendes verwenden:  
  
 [!code-vb[VbVbalrInterop#27](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/vbvbalrinterop/Class1.vb#27)]  
  
##  <a name="vbconinteroperabilitymarshalinganchor12"></a> Bereitstellen von Assemblys, die Interop verfügbar machen  
 Beim Bereitstellen von Assemblys, die COM‑Schnittstellen verfügbar machen, sind einige besondere Herausforderungen zu bewältigen.  Beispielsweise entsteht ein potenzielles Problem, wenn separate Anwendungen auf die gleiche COM\-Assembly verweisen.  Diese Situation tritt häufig ein, wenn eine neue Version einer Assembly installiert wird und gleichzeitig eine andere Anwendung noch die alte Version der Assembly verwendet.  Wenn eine Assembly mit einer gemeinsam verwendeten DLL deinstalliert wird, steht diese DLL den anderen Assemblys möglicherweise nicht mehr zur Verfügung.  
  
 Um dies zu verhindern, installieren Sie freigegebene Assemblys im globalen Assemblycache und verwenden für die Komponenten ein Mergemodul.  Wenn Sie die Anwendung nicht im GAC installieren können, installieren Sie sie in einem versionsspezifischen Unterverzeichnis des CommonFilesFolder.  
  
 Nicht freigegebene Assemblys sollten sich im gleichen Verzeichnis befinden wie die aufrufende Anwendung.  
  
## Siehe auch  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>   
 [COM Interop](../../../visual-basic/programming-guide/com-interop/index.md)   
 [Tlbimp.exe \(Type Library Importer\)](../Topic/Tlbimp.exe%20\(Type%20Library%20Importer\).md)   
 [Tlbexp.exe \(Type Library Exporter\)](../Topic/Tlbexp.exe%20\(Type%20Library%20Exporter\).md)   
 [Walkthrough: Implementing Inheritance with COM Objects](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)   
 [Inherits Statement](../../../visual-basic/language-reference/statements/inherits-statement.md)   
 [Globaler Assemblycache](../Topic/Global%20Assembly%20Cache.md)
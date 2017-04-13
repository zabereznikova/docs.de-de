---
title: "Kompilierung und Wiederverwendung in regul&#228;ren Ausdr&#252;cken | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Reguläre Ausdrücke von .NET Framework, Kompilierung"
  - "Reguläre Ausdrücke von .NET Framework, Module"
  - "Kompilierung, Reguläre Ausdrücke"
  - "Analysieren von Text mit regulären Ausdrücken, Kompilierung"
  - "Mustervergleich mit regulären Ausdrücken, Kompilierung"
  - "Reguläre Ausdrücke, Kompilierung"
  - "Reguläre Ausdrücke, Module"
  - "Suchen mit regulären Ausdrücken, Kompilierung"
ms.assetid: 182ec76d-5a01-4d73-996c-0b0d14fcea18
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# Kompilierung und Wiederverwendung in regul&#228;ren Ausdr&#252;cken
Sie können die Leistung von Anwendungen, die umfassenden Gebrauch von regulären Ausdrücken machen, optimieren, indem Sie sich vergegenwärtigen, wie das Modul für reguläre Ausdrücke Ausdrücke kompiliert und wie reguläre Ausdrücke zwischengespeichert werden.  In diesem Thema werden sowohl die Kompilierung als auch die Zwischenspeicherung erläutert.  
  
## Kompilierte reguläre Ausdrücke  
 Standardmäßig kompiliert das Modul für reguläre Ausdrücke einen regulären Ausdruck in eine Folge interner Anweisungen \(diese bestehen aus Codes hoher Ebene, die sich von denen in MSIL \(Microsoft Intermediate Language\) unterscheiden\).  Wenn das Suchmodul einen regulären Ausdruck ausführt, interpretiert es die internen Codes.  
  
 Wird ein <xref:System.Text.RegularExpressions.Regex>\-Objekt mit der <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName>\-Option erstellt, wird der reguläre Ausdruck in expliziten MSIL\-Code kompiliert und nicht in die für reguläre Ausdrücke üblicherweise verwendeten internen Anweisungen in Hochsprache.  Dadurch kann der JIT \(Just\-In\-Time\)\-Compiler von .NET Framework den Ausdruck in systemeigenen Maschinencode konvertieren, um höhere Ausführungsgeschwindigkeiten zu erzielen.  
  
 Allerdings kann generierter MSIL\-Code nicht entladen werden.  Die einzige Möglichkeit zur Entladung von Code besteht darin, die gesamte Anwendungsdomäne zu entladen \(d. h. den gesamten Code der Anwendung\).  Wenn ein regulärer Ausdruck mit der <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName>\-Option kompiliert wurde, werden die von dem kompilierten Ausdruck verwendeten Ressourcen von .NET Framework nie mehr freigegeben, auch wenn der reguläre Ausdruck von einem <xref:System.Text.RegularExpressions.Regex>\-Objekt erstellt wurde, das selbst für die Garbage Collection freigegeben wird.  
  
 Begrenzen Sie auf jeden Fall die Anzahl der verschiedenen regulären Ausdrücke, die Sie mit der <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName>\-Option kompilieren, um einen zu hohen Ressourcenverbrauch zu vermeiden.  Ist eine Anwendung auf eine große Zahl regulärer Ausdrücke angewiesen, sollten diese interpretiert und nicht kompiliert werden.  Wird wiederholt eine kleine Anzahl derselben regulären Ausdrücke verwendet, sollten diese mit der <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName>\-Option kompiliert werden, um eine höhere Leistung zu erzielen.  Als Alternative können auch vorkompilierte reguläre Ausdrücke verwendet werden.  Alle Ausdrücke können mit der <xref:System.Text.RegularExpressions.Regex.CompileToAssembly%2A>\-Methode in eine wiederverwendbare DLL kompiliert werden.  Dadurch kann eine Kompilierung zur Laufzeit vermieden und der Geschwindigkeitsvorteil kompilierter regulärer Ausdrücke ausgenutzt werden.  
  
## Der Cache für reguläre Ausdrücke  
 Um die Leistung zu verbessern, verfügt das Modul für reguläre Ausdrücke über einen anwendungsweiten Cache mit kompilierten regulären Ausdrücken.  Im Cache werden Muster regulärer Ausdrücke gespeichert, die nur in statischen Methodenaufrufen verwendet werden. \(An Instanzmethoden übergebene Muster regulärer Ausdrücke werden nicht zwischengespeichert.\) Dadurch wird vermieden, dass Ausdrücke bei jeder Verwendung erneut analysiert und in Bytecode höherer Ebene kompiliert werden müssen.  
  
 Die maximale Anzahl der zwischengespeicherten regulären Ausdrücke wird durch den Wert der `static` \(`Shared` in Visual Basic\) <xref:System.Text.RegularExpressions.Regex.CacheSize%2A?displayProperty=fullName>\-Eigenschaft festgelegt.  Standardmäßig speichert das Modul für reguläre Ausdrücke bis zu 15 kompilierte reguläre Ausdrücke zwischen.  Wenn die Anzahl der kompilierten regulären Ausdrücke die Größe das Cache überschreitet, wird der am längsten nicht verwendete reguläre Ausdruck verworfen und der neue reguläre Ausdruck zwischengespeichert.  
  
> [!IMPORTANT]
>  Die Methode der Zwischenspeicherung von regulären Ausdrücken in .NET Framework, Version 2.0, unterscheidet sich deutlich von der in .NET Framework, Version 1.0 und 1.1.  In .NET Framework 1.0 und 1.1 werden alle regulären Ausdrücke, sowohl die in statischen Methodenaufrufen als auch die in Instanzmethodenaufrufen verwendeten, zwischengespeichert.  Der Cache wird automatisch erweitert, um neue reguläre Ausdrücke zu speichern.  In .NET Framework 2.0 werden nur reguläre Ausdrücke zwischengespeichert, die in statischen Methodenaufrufen verwendet werden.  Standardmäßig werden die letzten 15 regulären Ausdrücke zwischengespeichert, wobei die Größe des Cache jedoch durch das Festlegen eines anderen Werts für die <xref:System.Text.RegularExpressions.Regex.CacheSize%2A>\-Eigenschaft geändert werden kann.  
  
 Es gibt zwei Möglichkeiten, wie die Anwendung vorkompilierte reguläre Ausdrücke nutzen kann:  
  
-   Durch die Verwendung einer statischen Methode des <xref:System.Text.RegularExpressions.Regex>\-Objekts zum Definieren des regulären Ausdrucks.  Wenn Sie ein Muster für reguläre Ausdrücke verwenden, das bereits in einem anderen statischen Methodenaufruf definiert wurde, ruft das Modul für reguläre Ausdrücke dieses aus dem Cache ab.  Ist dies nicht der Fall, kompiliert das Modul den regulären Ausdruck und fügt ihn zum Cache hinzu.  
  
-   Durch die Wiederverwendung eines vorhandenen <xref:System.Text.RegularExpressions.Regex>\-Objekts, solange sein Muster des regulären Ausdrucks benötigt wird.  
  
 Aufgrund des Mehraufwands, der durch die Objektinstanziierung und Kompilierung von regulären Ausdrücken anfällt, stellt das Erstellen und schnelle Löschen zahlreicher <xref:System.Text.RegularExpressions.Regex>\-Objekte einen sehr kostspieligen Prozess dar.  Sie können die Leistung von Anwendungen, die zahlreiche verschiedene reguläre Ausdrücke verwenden, optimieren, indem Sie Aufrufe statischer `Regex`\-Methoden verwenden und gegebenenfalls den Cache für reguläre Ausdrücke vergrößern.  
  
## Siehe auch  
 [Reguläre Ausdrücke von .NET Framework](../../../docs/standard/base-types/regular-expressions.md)
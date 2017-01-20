---
title: "/errorreport (C# Compiler Options) | Microsoft Docs"
ms.custom: ""
ms.date: "01/05/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/errorreport"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "-errorreport compiler option [C#]"
  - "errorreport compiler option [C#]"
  - "/errorreport compiler option [C#]"
ms.assetid: bd0e7493-b79d-4369-9c3f-ba26ebdfbedf
caps.latest.revision: 35
caps.handback.revision: 35
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# /errorreport (C# Compiler Options)
Diese Option bietet eine komfortable Möglichkeit, einen internen C\#\-Compilerfehler an Microsoft zu melden.  
  
> [!NOTE]
>  In Windows Vista und Windows Server 2008 überschreiben die Fehlerberichteinstellungen, die Sie für Visual Studio festlegen, nicht die über Windows Error Reporting \(WER\) festgelegten Einstellungen.  WER\-Einstellungen haben immer Vorrang vor Visual Studio\-Fehlerberichteinstellungen.  
  
## Syntax  
  
```  
/errorreport:{ none | prompt | queue | send }  
```  
  
## Argumente  
 **none**  
 Berichte zu internen Compilerfehlern werden nicht gesammelt oder an Microsoft gesendet.  
  
 **prompt**  
 Sie werden aufgefordert, einen Bericht zu senden, wenn Sie einen internen Compilerfehler empfangen.  **prompt** ist der Standard, wenn Sie eine Anwendung in der Entwicklungsumgebung kompilieren.  
  
 **queue**  
 Der Fehlerbericht wird in die Warteschleife eingereiht.  Wenn Sie sich mit Administratoranmeldeinformationen anmelden, können Sie alle Fehler seit der letzten Anmeldung angeben.  Sie werden nur alle drei Tage dazu aufgefordert, Berichte für Fehler zu senden.  **queue** ist der Standard, wenn eine Anwendung in der Befehlszeile kompiliert wird.  
  
 **send**  
 Berichte über interne Compilerfehler werden automatisch an Microsoft gesendet.  Um diese Option zu aktivieren, müssen Sie zuerst der Datensammlungsrichtlinie von Microsoft zustimmen.  Wenn Sie **\/errorreport:send** das erste Mal auf einem Computer angeben, werden Sie in einer Compilermeldung auf eine Website mit der Datensammlungsrichtlinie von Microsoft verwiesen.  
  
 Diese Option hängt von den Registrierungseinstellungen ab.  Weitere Informationen darüber, wie die entsprechenden Werte in der Registrierung, finden Sie auf [Verwenden von automatischen Fehlerbericht in Visual Studio 2008\-Befehlszeilentools einschaltet](http://go.microsoft.com/fwlink/?LinkID=184695) der MSDN\-Website festlegt.  
  
## Hinweise  
 Ein interner Compilerfehler tritt auf, wenn der Compiler eine Quellcodedatei nicht verarbeiten kann.  Bei Auftreten eines internen Compilerfehlers wird vom Compiler keine Ausgabedatei oder hilfreiche Analyse erstellt, die Sie zum Beheben des Fehlers im Code verwenden können.  
  
 In früheren Versionen wurden Sie beim Auftreten eines internen Compilerfehlers aufgefordert, das Problem dem Microsoft\-Produktsupport zu melden.  Mit **\/errorreport** können Sie die Informationen über den internen Compilerfehler direkt an das Visual C\#\-Team weiterleiten.  Die Fehlerberichte können dazu beitragen, zukünftige Compilerversionen zu verbessern.  
  
 Ob Benutzer Berichte versenden können, ist von den Computer\- und den Benutzerberechtigungen abhängig.  
  
 Weitere Informationen über Fehlerdebugger, Sie finden [Beschreibung des Dr. Watson Tool für Windows \(Drwtsn32.exe\)](http://go.microsoft.com/fwlink/?LinkId=147286).  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie die **Eigenschaften**\-Seite des Projekts.  Weitere Informationen finden Sie unter [Seite "Erstellen", Projekt\-Designer \(C\#\)](/visual-studio/ide/reference/build-page-project-designer-csharp).  
  
2.  Klicken Sie auf die Eigenschaftenseite **Erstellen**.  
  
3.  Klicken Sie auf die Schaltfläche **Erweitert**.  
  
4.  Ändern Sie die Eigenschaft **Bericht für internen Compilerfehler**.  
  
 Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.CSharpProjectConfigurationProperties3.ErrorReport%2A>.  
  
## Siehe auch  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)
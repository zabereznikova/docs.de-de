---
title: "&#220;berblick &#252;ber die Interoperabilit&#228;t (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "C#-Sprache, Interoperabilität"
  - "C++ Interop"
  - "COM-Interop"
  - "Interoperabilität, Informationen über Interoperabilität"
  - "Plattformaufruf"
ms.assetid: c025b2e0-2357-4c27-8461-118f0090aeff
caps.latest.revision: 43
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 43
---
# &#220;berblick &#252;ber die Interoperabilit&#228;t (C#-Programmierhandbuch)
In diesem Thema sind Methoden beschrieben, mit denen die Interoperabilität zwischen verwaltetem C\#\-Code und nicht verwalteten Code ermöglicht wird.  
  
## Plattformaufruf  
 Der *Plattformaufruf* ist ein Dienst, mit dem nicht verwaltete Funktionen, die in DLLs \(Dynamic Link Libraries\) implementiert sind \(z. B. in der Microsoft Win32\-API\), von verwaltetem Code aufgerufen werden können.  Durch diesen Dienst wird eine exportierte Funktion gesucht und aufgerufen, und die dazugehörigen Argumente \(ganze Zahlen, Zeichenfolgen, Arrays, Strukturen usw.\) werden gegebenenfalls über die Grenzen der Interoperation hinaus gemarshallt.  
  
 Weitere Informationen finden Sie unter [Consuming Unmanaged DLL Functions](../Topic/Consuming%20Unmanaged%20DLL%20Functions.md) und [Gewusst wie: Verwenden eines Plattformaufrufs zum Wiedergeben einer Wavedatei](../../../csharp/programming-guide/interop/how-to-use-platform-invoke-to-play-a-wave-file.md).  
  
> [!NOTE]
>  Die [Common Language Runtime](../Topic/Common%20Language%20Runtime%20\(CLR\).md) \(CLR\) verwaltet den Zugriff auf Systemressourcen.  Durch das Aufrufen von nicht verwaltetem Code außerhalb der CLR wird dieser Sicherheitsmechanismus umgangen, deshalb stellt diese Vorgehensweise ein Sicherheitsrisiko dar.  Beispielsweise können Ressourcen in nicht verwaltetem Code direkt von nicht verwaltetem Code aufgerufen werden, indem der CLR\-Sicherheitsmechanismus umgegangen wird.  Informationen finden Sie unter [.NET Framework Security](http://go.microsoft.com/fwlink/?LinkId=37122).  
  
## C\+\+ Interop  
 Sie können C\+\+\-Interop, auch als IJW \(It Just Works\) bezeichnet, zum Umschließen einer systemeigenen C\+\+\-Klasse verwenden, sodass diese von Code verarbeitet werden kann, der in C\# oder einer anderen .NET Framework\-Programmiersprache erstellt wurde.  Dazu schreiben Sie C\+\+\-Code, um eine systemeigene DLL oder COM\-Komponente zu umschließen.  Im Gegensatz zu anderen .NET Framework\-Programmiersprachen verfügt [!INCLUDE[vcprvc](../../../csharp/programming-guide/interop/includes/vcprvc-md.md)] über Interoperabilitätsunterstützung, mit der verwalteter und nicht verwalteter Code in derselben Anwendung und sogar in derselben Datei vorhanden sein können.  Dann erstellen Sie den C\+\+\-Code mit dem **\/clr**\-Compilerschalter, um eine verwaltete Assembly zu erzeugen.  Letztlich fügen Sie der Assembly im C\#\-Projekt einen Verweis hinzu und verwenden die umschlossenen Objekte wie jede andere verwaltete Klasse.  
  
## Verfügbarmachen von COM\-Komponenten für C\#  
 Sie können eine COM\-Komponente aus einem C\#\-Projekt verwenden.  Dazu müssen Sie die folgenden allgemeinen Schritte ausführen:  
  
1.  Suchen Sie eine COM\-Komponente, die Sie verwenden möchten, und registrieren Sie diese.  Verwenden Sie regsvr32.exe, um eine COM\-DLL zu registrieren oder die Registrierung aufzuheben.  
  
2.  Fügen Sie dem Projekt einen Verweis auf die COM\-Komponente oder Typbibliothek hinzu.  
  
     Wenn Sie den Verweis hinzufügen, gibt [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs-md.md)] eine .NET Framework\-Interop\-Assembly mit dem [Tlbimp.exe \(Type Library Importer\)](../Topic/Tlbimp.exe%20\(Type%20Library%20Importer\).md) aus, der eine Typbibliothek als Eingabe akzeptiert.  Die Assembly, auch als RCW \(Runtime Callable Wrapper\) bezeichnet, enthält verwaltete Klassen und Schnittstellen, die die COM\-Klassen und Schnittstellen in der Typbibliothek umschließen.  [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs-md.md)] fügt dem Projekt einen Verweis auf die generierte Assembly hinzu.  
  
3.  Erstellen Sie eine Instanz einer im RCW definierten Klasse.  Diese wiederum erstellt eine Instanz des COM\-Objekts.  
  
4.  Verwenden Sie das Objekt genau wie jedes andere verwaltete Objekt.  Wenn das Objekt von der Garbage Collection zurückgefordert wird, wird die Instanz des COM\-Objekts vom Speicher ebenfalls freigegeben.  
  
 Weitere Informationen finden Sie unter [Exposing COM Components to the .NET Framework](../Topic/Exposing%20COM%20Components%20to%20the%20.NET%20Framework.md).  
  
## Verfügbarmachen von C\# für COM  
 COM\-Clients können C\#\-Typen verwenden, die ordnungsgemäß verfügbar gemacht wurden.  Mit den folgenden Grundschritten machen Sie C\#\-Typen verfügbar:  
  
1.  Fügen Sie im C\#\-Projekt Interop\-Attribute hinzu.  
  
     Sie können ein Assembly\-COM sichtbar machen, indem Sie [!INCLUDE[csprcs](../../../csharp/includes/csprcs-md.md)]\-Projekteigenschaften ändern.  Weitere Informationen finden Sie unter [Dialogfeld "Assemblyinformationen"](/visual-studio/ide/reference/assembly-information-dialog-box).  
  
2.  Generieren Sie eine COM\-Typbibliothek, und registrieren Sie diese für die Verwendung durch COM.  
  
     Sie können [!INCLUDE[csprcs](../../../csharp/includes/csprcs-md.md)]\-Projekteigenschaften ändern, um die C\#\-Assembly für COM\-Interop automatisch zu registrieren.  [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs-md.md)] verwendet das [Regasm.exe \(Assembly Registration Tool\)](../Topic/Regasm.exe%20\(Assembly%20Registration%20Tool\).md) mit dem `/tlb`\-Befehlszeilenschalter, der eine verwaltete Assembly als Eingabe erfordert, um eine Typbibliothek zu generieren.  Diese Typbibliothek beschreibt die `public`\-Typen in der Assembly und fügt Registrierungseinträge hinzu, sodass COM\-Clients verwaltete Klassen erstellen können.  
  
 Weitere Informationen finden Sie unter [Exposing .NET Framework Components to COM](../Topic/Exposing%20.NET%20Framework%20Components%20to%20COM.md) und [COM\-Beispielklasse](../../../csharp/programming-guide/interop/example-com-class.md).  
  
## Siehe auch  
 [Improving Interop Performance](http://go.microsoft.com/fwlink/?LinkId=99564)   
 [Introduction to COM Interop](http://go.microsoft.com/fwlink/?LinkId=112406)   
 [Marshaling between Managed and Unmanaged Code](http://go.microsoft.com/fwlink/?LinkId=112398)   
 [Interoperating with Unmanaged Code](../Topic/Interoperating%20with%20Unmanaged%20Code.md)   
 [Advanced COM Interoperability](http://msdn.microsoft.com/de-de/3ada36e5-2390-4d70-b490-6ad8de92f2fb)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)
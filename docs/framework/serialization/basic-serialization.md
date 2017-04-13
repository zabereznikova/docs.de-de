---
title: "Einfache Serialisierung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "Binäre Serialisierung, Einfache Serialisierung"
  - "Serialisierung, Einfache Serialisierung"
ms.assetid: d899d43c-335a-433e-a589-cd187192984f
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# Einfache Serialisierung
Die einfachste Möglichkeit, eine Klasse serialisierbar zu machen, besteht darin, sie folgendermaßen mit dem [Serializable](frlrfSystemSerializableAttributeClassTopic)\-Attribut zu markieren.  
  
```csharp  
[Serializable]  
public class MyObject {  
  public int n1 = 0;  
  public int n2 = 0;  
  public String str = null;  
}  
```  
  
 Das nachstehende Codebeispiel zeigt, wie eine Instanz dieser Klasse in eine Datei serialisiert werden kann.  
  
```csharp  
MyObject obj = new MyObject();  
obj.n1 = 1;  
obj.n2 = 24;  
obj.str = "Some String";  
IFormatter formatter = new BinaryFormatter();  
Stream stream = new FileStream("MyFile.bin", FileMode.Create, FileAccess.Write, FileShare.None);  
formatter.Serialize(stream, obj);  
stream.Close();  
```  
  
 In diesem Beispiel wird ein binäres Formatierungsprogramm zur Durchführung der Serialisierung verwendet.Sie müssen lediglich eine Instanz des Streams und des zu verwendenden Formatierungsprogramms erstellen, und im Formatierungsprogramm dann die **Serialize**\-Methode aufrufen.Der Stream und das zu serialisierende Objekt werden in diesem Aufruf als Parameter angegeben.Obwohl es in diesem Beispiel nicht ausdrücklich gezeigt wird, werden alle Membervariablen einer Klasse serialisiert, auch wenn Variablen als privat markiert sind.In dieser Hinsicht unterscheidet sich die binäre Serialisierung von der [XMLSerializer\-Klasse](https://msdn.microsoft.com/en-us/library/system.xml.serialization.xmlserializer.aspx), die nur öffentliche Felder serialisiert.Informationen dazu, wie Membervariablen von der binären Serialisierung ausgeschlossen werden, finden Sie unter [Selektive Serialisierung](../../../docs/framework/serialization/selective-serialization.md).  
  
 Es ist ebenso einfach, das Objekt wieder in seinem früheren Zustand wiederherzustellen.Erstellen Sie zunächst einen Stream zum Einlesen und ein [Formatierungsprogramm](frlrfSystemRuntimeSerializationFormatterClassTopic), und weisen Sie dieses dann an, das Objekt zu deserialisieren.Das nachfolgende Codebeispiel zeigt, wie Sie hierzu vorgehen.  
  
```csharp  
IFormatter formatter = new BinaryFormatter();  
Stream stream = new FileStream("MyFile.bin", FileMode.Open, FileAccess.Read, FileShare.Read);  
MyObject obj = (MyObject) formatter.Deserialize(stream);  
stream.Close();  
  
// Here's the proof.  
Console.WriteLine("n1: {0}", obj.n1);  
Console.WriteLine("n2: {0}", obj.n2);  
Console.WriteLine("str: {0}", obj.str);  
```  
  
 Die oben verwendete [BinaryFormatter](frlrfSystemRuntimeSerializationFormattersBinaryBinaryFormatterClassTopic)\-Klasse ist sehr effizient und erzeugt einen kompakten Bytestream.Alle Objekte, die mit diesem Formatierungsprogramm serialisiert wurden, können mit diesem auch deserialisiert werden. Dadurch ist es das optimale Tool zur Serialisierung von Objekten, die im .NET Framework deserialisiert werden.Beachten Sie unbedingt, dass beim Deserialisieren von Objekten keine Konstruktoren aufgerufen werden.Diese Einschränkung wird der Deserialisierung auferlegt, um die Leistung zu verbessern.Dies verstößt jedoch gegen einige der üblichen Verträge, die die Runtime mit dem Objektentwickler schließt, und Entwickler müssen sich über die Auswirkungen im Klaren sein, die die Markierung eines Objekts als serialisierbar hat.  
  
 Wenn Portabilität gefordert ist, verwenden Sie stattdessen die [SoapFormatter](frlrfSystemRuntimeSerializationFormattersSoapSoapFormatterClassTopic)\-Klasse.Ersetzen Sie einfach im oben dargestellten Code die **BinaryFormatter**\-Klasse durch die **SoapFormatter,**\-Klasse, und rufen Sie wie zuvor **Serialize** und **Deserialize** auf.Dieses Formatierungsprogramm erzeugt die folgende Ausgabe für das oben dargestellte Beispiel.  
  
```  
<SOAP-ENV:Envelope  
  xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"  
  xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
  xmlns:SOAP- ENC="http://schemas.xmlsoap.org/soap/encoding/"  
  xmlns:SOAP- ENV="http://schemas.xmlsoap.org/soap/envelope/"  
  SOAP-ENV:encodingStyle=  
  "http://schemas.microsoft.com/soap/encoding/clr/1.0"  
  "http://schemas.xmlsoap.org/soap/encoding/"  
  xmlns:a1="http://schemas.microsoft.com/clr/assem/ToFile">  
  
  <SOAP-ENV:Body>  
    <a1:MyObject id="ref-1">  
      <n1>1</n1>  
      <n2>24</n2>  
      <str id="ref-3">Some String</str>  
    </a1:MyObject>  
  </SOAP-ENV:Body>  
</SOAP-ENV:Envelope>  
```  
  
 Sie müssen unbedingt beachten, dass das **Serializable**\-Attribut nicht geerbt werden kann.Wenn Sie eine neue Klasse von `MyObject` ableiten, muss diese neue Klasse auch mit dem Attribut markiert werden, da sie sonst nicht serialisiert werden kann.Wenn Sie beispielsweise eine Instanz der nachstehenden Klasse zu serialisieren versuchen, wird eine Ausnahme des Typs [SerializationException](frlrfSystemRuntimeSerializationSerializationExceptionClassTopic) ausgelöst, die Sie darüber informiert, dass der `MyStuff`\-Typ nicht als serialisierbar markiert ist.  
  
```csharp  
public class MyStuff : MyObject   
{  
  public int n3;  
}  
```  
  
 Die Verwendung des **Serializable**\-Attributs ist zweckmäßig, aber auch mit den oben beschriebenen Einschränkungen verbunden.Informationen dazu, wie eine Klasse für die Serialisierung markiert wird, finden Sie unter [Serialisierungsrichtlinien](../../../docs/framework/serialization/serialization-guidelines.md). Die Serialisierung kann nicht hinzugefügt werden, nachdem eine Klasse kompiliert wurde.  
  
## Siehe auch  
 [Binäre Serialisierung](../../../docs/framework/serialization/binary-serialization.md)   
 [Remote Objects](http://msdn.microsoft.com/de-de/515686e6-0a8d-42f7-8188-73abede57c58)   
 [XML\- und SOAP\-Serialisierung](../../../docs/framework/serialization/xml-and-soap-serialization.md)
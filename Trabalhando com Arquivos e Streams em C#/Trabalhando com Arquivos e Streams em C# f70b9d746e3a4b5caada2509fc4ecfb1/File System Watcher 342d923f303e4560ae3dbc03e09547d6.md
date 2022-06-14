# File System Watcher

### Teoria

- Permite monitorar eventos de modificação em diretórios e arquivos, através do disparo de eventos

### Demo

```csharp
var path = @"C:\workspace\CSharp-estudos\Trabalhando com Arquivos e Streams em C#\Directory_And_DirectoryInfo\globo";

using var fsw = new FileSystemWatcher(path);

fsw.Created += OnCreated;
fsw.Deleted += OnDeleted;
fsw.Renamed += OnRenamed;

fsw.EnableRaisingEvents = true;
fsw.IncludeSubdirectories = true;

System.Console.WriteLine($"Monitorando eventos na pasta {path}");
System.Console.WriteLine("[enter] para finalizar...");
Console.ReadKey();

void OnCreated(object sender, FileSystemEventArgs e)
{
    System.Console.WriteLine($"Foi criado o arquivo {e.Name}");
}

void OnDeleted(object sender, FileSystemEventArgs e)
{
    System.Console.WriteLine($"Foi deletado o arquivo {e.Name}");
}

void OnRenamed(object sender, RenamedEventArgs e)
{
    System.Console.WriteLine($"O arquivo {e.OldName} foi renomeado para {e.Name}");
}
```
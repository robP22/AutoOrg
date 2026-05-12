# AutoOrg v0.1.0

A privacy-focused, cross-platform desktop application for organizing and unorganizing files using intelligent metadata-based categorization and flexible organization strategies.

Built with zero data collection and fully local-only processing, AutoOrg runs entirely on your device while providing both structure creation (organizing messy directories) and structure reversal (unorganizing flattened systems). It includes real-time progress tracking, configurable rules, and safe file operations with robust error handling.


## Key Features

- Dual functionality for organizing and unorganizing file structures  
- Smart organization using metadata, file age, and adaptive rules  
- Multiple organization modes: Smart, Date-based, and Type-based  
- Fully local execution with zero telemetry or network dependencies  
- Cross-platform support for Windows, macOS, and Linux  
- Real-time progress tracking and status updates  
- Native file system integration and safe path handling  
- Event-driven architecture with decoupled services  


## System Capabilities

AutoOrg processes files using metadata-aware rules, classification logic, and structured directory strategies.

### Organization
- Intelligent file placement based on metadata, file age, and adaptive rules  
- Date-based hierarchy using year/month directory structures  
- Type-based grouping (images, videos, documents, audio, other)  
- Metadata extraction from EXIF data, media tags, and document properties  
- Consistent time-based structuring using creation, modification, or embedded timestamps  
- Fallback logic using type-first grouping when metadata is unavailable  

### Unorganization
- Recursive flattening of nested directory structures  
- Automatic filename conflict resolution during consolidation  
- Independent processing pipeline separate from organization logic  
- Safe traversal and normalization of deeply nested directories  

### Interface Behavior
- Real-time progress tracking (processed vs total files)  
- Clear operation states (ready, processing, error)  
- Directory-based workflow with source and destination selection  
- Integrated error reporting with recovery options  


## Privacy & Security

- Fully local processing with no internet or cloud communication  
- Zero telemetry, analytics, or usage tracking  
- Configurable metadata extraction controls  
- Input validation and directory traversal protection  
- Sanitized and configurable error output detail levels  
- Safe file operations with pre-execution validation  


## Cross-Platform Support

- Native support for Windows, macOS, and Linux  
- Platform-aware path normalization and filesystem handling  
- Integration with native file explorers  
- Consistent behavior across operating systems  
- UI behavior adapted to platform conventions  


## Architecture Overview

AutoOrg is built using a modular, event-driven architecture with independent services.

### Design Principles
- Event-driven communication for loose coupling  
- Microservice-style internal services for separation of concerns  
- Strategy pattern for interchangeable organization logic  
- Service injection for clean dependency management  

### Core Services
- OrganizationService: Handles intelligent file organization  
- UnorganizeService: Manages directory flattening operations  
- FileService: Cross-platform file operations and validation  
- MetadataService: Extracts and analyzes file metadata  
- GUI Layer: PySide6-based interface with native integration  


## Technology Stack

### Framework
- PySide6 (Qt for Python) for cross-platform GUI  

### Core Libraries
- pathlib, shutil for file system operations  
- ExifRead for image metadata  
- Pillow (PIL) for image inspection  
- python-magic for file type detection  
- pymediainfo for audio/video metadata  
- python-docx and PyPDF2 for document parsing 


## Project Structure
```
src/
├── core/
│   ├── events.py
│   ├── protocols.py
│   ├── config_interface.py
│   └── validation_manager.py
├── models/
│   └── operation_result.py
├── services/
│   ├── core/
│   │   ├── organization_service.py
│   │   ├── unorganize_service.py
│   │   └── validation_service.py
│   ├── config/
│   │   ├── config_service.py
│   │   └── privacy_logger.py
│   ├── metadata/
│   │   ├── document_service.py
│   │   ├── exif_service.py
│   │   ├── media_service.py
│   │   └── metadata_service.py
│   ├── platform/
│   │   └── platform_service.py
├── organizers/
│   ├── base_organizer.py
│   ├── smart_organizer.py
│   ├── date_organizer.py
│   └── type_organizer.py
├── file_operations/
│   ├── file_info.py
│   ├── file_service.py
│   ├── file_utils.py
│   └── file_types.py
├── gui/
│   ├── main_window.py
│   └── privacy_dialog.py
├── pyproject.toml
├── main.py
└── README.md
```


## Quick Start

### Setup
1. Clone repository 
2. Install Python 3.9.6  
3. Create virtual environment: `python3.9 -m venv .venv`  
4. Install dependencies: `uv sync`  
5. Run application: `python3 src/main.py`  

### Usage
1. Launch application  
2. Select source directory  
3. Select destination directory  
4. Choose operation (Organize or Unorganize)  
5. Monitor real-time progress  
6. View results summary  


## Contributing

Contributions are welcome with prior coordination.

### Setup
- Fork repository  
- Install dependencies using uv  
- Follow existing architecture patterns  
- Maintain event-driven structure  

### Guidelines
- Use type hints  
- Include docstrings  
- Write unit tests where applicable  
- Follow service separation patterns  


## License

MIT License


## Support

For issues, feature requests, or contributions:
- GitHub Issues for bug reports and feature requests

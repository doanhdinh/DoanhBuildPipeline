# Doanh Build Pipeline - Hướng dẫn sử dụng

## Cài đặt Package

### Cách 1: Qua Unity Package Manager (Khuyến nghị)

1. Mở Unity Project
2. Vào **Window > Package Manager**
3. Click **+** > **Add package from git URL**
4. Nhập URL: `https://github.com/YOUR_USERNAME/DoanhBuildPipeline.git`

### Cách 2: Qua manifest.json

Thêm vào file `Packages/manifest.json`:

```json
{
  "dependencies": {
    "com.doanh.buildpipeline": "https://github.com/YOUR_USERNAME/DoanhBuildPipeline.git#v1.5.9"
  }
}
```

## Sử dụng Package

### 1. Tạo Build Configuration

1. Vào **Assets > Create > Build Pipeline > Build Configuration**
2. Cấu hình các môi trường:
   - **Staging**: Cho development team
   - **UAT**: Cho testing
   - **Production**: Cho release

### 2. Sử dụng trong CI/CD

```csharp
// Gọi build từ command line hoặc script
Doanh.BuildPipeline.DoanhAzureDevops.PerformBuild();
```

### 3. Command Line Arguments

```bash
# Build Android APK
DoanhAzureDevops.PerformBuild() -buildTarget Android -outputPath ./Builds -configuration Production

# Build iOS Xcode Project
DoanhAzureDevops.PerformBuild() -buildTarget iOS -outputPath ./Builds -configuration Production

# Build WebGL
DoanhAzureDevops.PerformBuild() -buildTarget WebGL -outputPath ./Builds -configuration Production
```

## Tính năng chính

- ✅ Multi-platform build (Android, iOS, WebGL, Standalone)
- ✅ Environment management (Staging, UAT, Production)
- ✅ Addressable assets support
- ✅ CI/CD integration
- ✅ Audio optimization for WebGL
- ✅ Scripting define symbols management

## Phiên bản

- **Version**: 1.5.9
- **Unity**: 2021.3+
- **Type**: Tool (Editor only) 
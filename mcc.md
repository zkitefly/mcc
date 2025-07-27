# My-Clash-Config

[教程页面](/mcct.md)

## 客户端

### 推荐版本

<!-- ClashMetaForAndroid 下载 -->
<div class="repo-section">
    <h4 class="repo-title">Android 版本</h4>
    <div id="status-meta" class="loading">正在获取最新版本信息...</div>
    <div id="download-container-meta"></div>
</div>

<!-- ClashVergeRev 下载 -->
<div class="repo-section">
    <h4 class="repo-title">Windows 版本</h4>
    <div id="status-verge" class="loading">正在获取最新版本信息...</div>
    <div id="download-container-verge"></div>
</div>

<script>
    document.addEventListener('DOMContentLoaded', function() {
        // 获取 ClashMetaForAndroid 最新版本
        fetch('https://gh-proxy.com/https://api.github.com/repos/MetaCubeX/ClashMetaForAndroid/releases/latest')
            .then(response => {
                if (!response.ok) throw new Error('网络响应不正常');
                return response.json();
            })
            .then(data => {
                const statusElement = document.getElementById('status-meta');
                const downloadContainer = document.getElementById('download-container-meta');
                
                // 查找 meta-arm64-v8a-release.apk
                const asset = data.assets.find(asset => 
                    asset.name.endsWith('meta-arm64-v8a-release.apk')
                );

                if (asset) {
                    statusElement.textContent = `最新版本: ${data.tag_name}`;
                    statusElement.className = '';
                    
                    const proxyUrl = 'https://gh-proxy.com/' + asset.browser_download_url;
                    const downloadLink = document.createElement('a');
                    downloadLink.href = proxyUrl;
                    downloadLink.className = 'download-link';
                    downloadLink.textContent = `${asset.name}`;
                    downloadLink.target = '_blank';
                    
                    downloadContainer.appendChild(downloadLink);
                } else {
                    throw new Error('未找到 meta-arm64-v8a-release.apk 文件');
                }
            })
            .catch(error => {
                document.getElementById('status-meta').textContent = `错误: ${error.message}`;
                document.getElementById('status-meta').className = 'error';
                console.error('ClashMetaForAndroid 获取失败:', error);
            });

        // 获取 ClashVerge Rev 最新版本
        fetch('https://gh-proxy.com/https://api.github.com/repos/clash-verge-rev/clash-verge-rev/releases/latest')
            .then(response => {
                if (!response.ok) throw new Error('网络响应不正常');
                return response.json();
            })
            .then(data => {
                const statusElement = document.getElementById('status-verge');
                const downloadContainer = document.getElementById('download-container-verge');
                
                // 查找 x64-setup.exe
                const asset = data.assets.find(asset => 
                    asset.name.endsWith('x64-setup.exe')
                );

                if (asset) {
                    statusElement.textContent = `最新版本: ${data.tag_name}`;
                    statusElement.className = '';
                    
                    const proxyUrl = 'https://gh-proxy.com/' + asset.browser_download_url;
                    const downloadLink = document.createElement('a');
                    downloadLink.href = proxyUrl;
                    downloadLink.className = 'download-link';
                    downloadLink.textContent = `${asset.name}`;
                    downloadLink.target = '_blank';
                    
                    downloadContainer.appendChild(downloadLink);
                } else {
                    throw new Error('未找到 x64-setup.exe 文件');
                }
            })
            .catch(error => {
                document.getElementById('status-verge').textContent = `错误: ${error.message}`;
                document.getElementById('status-verge').className = 'error';
                console.error('Clash Verge 获取失败:', error);
            });
    });
</script>

### 其他链接

[Clash for Android 2.5.12.premium.apk](https://gh-proxy.com/https://github.com/zkitefly/zkitefly.github.io/releases/download/3/Clash.for.Android.2.5.12.premium.apk)

[clash-verge-rev](https://github.com/clash-verge-rev/clash-verge-rev/releases/latest)

[ClashMetaForAndroid](https://github.com/MetaCubeX/ClashMetaForAndroid/releases/latest)

[gh-proxy.com](https://gh-proxy.com)

[更多...](https://github.com/zkitefly/zkitefly.github.io/releases/tag/3)

## 配置文件

`https://zkitefly.no-mad-world.club/link/sd4JkXKkmuJQ4fyw?clash=3&extend=1`

`https://zkitefly.no-mad-world.club/link/3UyGi9l3Y9siXmjr?clash=3&extend=1`

`https://zkitefly.no-mad-world.club/link/bPFKzmOdPlIX4pKb?clash=3&extend=1`

`https://aa.dabai.in/link/z2SMogEehRtWyNWq?clash=1`

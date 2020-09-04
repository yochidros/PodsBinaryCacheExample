# Uncomment the next line to define a global platform for your project
platform :ios, '11.0'
plugin 'cocoapods-binary'
plugin 'cocoapods-binary-cache'

config_cocoapods_binary_cache(
  prebuild_config: "Debug",
  dev_pods_enabled: true
)

all_binary!
enable_bitcode_for_prebuilt_frameworks!
keep_source_code_for_prebuilt_frameworks!

target 'PodsBinaryCacheExample' do
  # Comment the next line if you don't want to use dynamic frameworks
  use_frameworks!

  pod 'RealmSwift'
end

post_install do |installer|
  installer.pods_project.targets.each do |target|
    target.build_configurations.each do |config|
      config.build_settings['BUILD_LIBRARY_FOR_DISTRIBUTION'] = 'YES' # Only work from Xcode 11
    end
  end
end

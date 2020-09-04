# Uncomment the next line to define a global platform for your project
platform :ios, '11.0'
plugin 'cocoapods-binary-cache'


target 'PodsBinaryCacheExample' do
  # Comment the next line if you don't want to use dynamic frameworks
  use_frameworks!

  pod 'RealmSwift', :binary=>true
end

post_install do |installer|
  installer.pods_project.targets.each do |target|
    target.build_configurations.each do |config|
      config.build_settings['BUILD_LIBRARY_FOR_DISTRIBUTION'] = 'YES' # Only work from Xcode 11
    end
  end
end

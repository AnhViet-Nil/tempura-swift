platform :ios, '10.0'

source 'https://github.com/CocoaPods/Specs.git'

inhibit_all_warnings!
use_frameworks!

target 'Tempura' do
  podspec

  target 'TempuraTests' do
    inherit! :search_paths
    pod 'Quick', '~> 1.3'
    pod 'Nimble', '~> 7.3'
  end

  target 'Demo' do
    pod 'PinLayout'
    pod 'DeepDiff', '~> 2.0'
  end

  target 'DemoTests' do
    inherit! :search_paths
    pod 'Quick', '~> 1.3'
    pod 'Nimble', '~> 7.3'
  end
end

target 'TempuraTesting' do
  podspec
  pod 'Tempura', :path => '.'
end

post_install do |installer|
  oldTargets = ['Quick', 'Nimble', 'DeepDiff']
 
  installer.pods_project.targets.each do |target|
    if oldTargets.include? target.name
      target.build_configurations.each do |config|
        config.build_settings['SWIFT_VERSION'] = '4.2'
      end
    end
  end
end
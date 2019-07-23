# Uncomment the next line to define a global platform for your project
platform :ios, '10.0'
use_frameworks!
install! 'cocoapods', :deterministic_uuids => false

source 'git@github.com:applicaster/CocoaPods.git'
source 'git@github.com:applicaster/PluginsBuilderCocoaPods.git'
source 'git@github.com:CocoaPods/Specs.git'
source 'git@github.com:parpiyaniamit/SugarBoxSDK.git'




def shared_pods

end

target 'SBInitializePlugin' do
    shared_pods

    pod 'SBInitializePlugin', :path => '/Users/amitparpiyani/sbinitializeplugin/SBInitializePlugin.podspec'
end

pre_install do |installer|
    # workaround for https://github.com/CocoaPods/CocoaPods/issues/3289
    Pod::Installer::Xcode::TargetValidator.send(:define_method, :verify_no_static_framework_transitive_dependencies) {}
end

post_install do |installer|
    installer.pods_project.targets.each do |target|
        target.build_configurations.each do |config|
            config.build_settings['SWIFT_VERSION'] = '4.2'
        end
    end
end

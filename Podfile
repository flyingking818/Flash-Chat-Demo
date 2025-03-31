#Swift Package Manager is a lightweight and integrated package manager for Swift-only projects, while CocoaPods is a more feature-rich third-party package manager with support for both Swift and Objective-C projects. The choice between them depends on the specific needs of the project and the preference of the developer.

#Updated the C references and fixed the compatibility issues of the app.


platform :ios, '16'


target 'Flash Chat iOS13' do
  use_frameworks!

  # Pods for Flash Chat iOS13
  pod 'Firebase/Auth'
  pod 'Firebase/Firestore'

end

post_install do |installer|
  installer.pods_project.targets.each do |target|
    if target.name == 'BoringSSL-GRPC'
      target.source_build_phase.files.each do |file|
        if file.settings && file.settings['COMPILER_FLAGS']
          flags = file.settings['COMPILER_FLAGS'].split
          flags.reject! { |flag| flag == '-GCC_WARN_INHIBIT_ALL_WARNINGS' }
          file.settings['COMPILER_FLAGS'] = flags.join(' ')
        end
      end
    end
  end
end

